# 🧩 zicPixel / zicBox Build & Debug Log

## ✅ Summary
This document records the full process of building, debugging, and configuring **zicPixel / zicBox** on a Raspberry Pi running Bookworm (ARM64/ARMHF).  
It includes installation, dependency setup, compilation, audio configuration, and hardware fixes.

---

## 🧱 Build Process

### Steps performed:
1. Installed dependencies:
   ```bash
   sudo apt install -y librtmidi-dev librtaudio-dev liblua5.4-dev libpulse-dev
   ```
2. Fixed missing `sndfile.h` by installing:
   ```bash
   sudo apt install -y libsndfile1-dev
   ```
3. Resolved build errors by editing source files:
   - Added `<algorithm>` to `draw/ST7789/draw.h` for `std::sort`
   - Fixed `std::max({})` usage in `ValueComponent.h`
   - Installed missing headers (`RtMidi.h`, `lua.h`)

4. Rebuilt with:
   ```bash
   make pixel
   ```

---

## 🎧 PCM5102 I²S Audio Setup

### Config file edited:
`/boot/firmware/config.txt`

### Added lines:
```ini
# --- Enable PCM5102 / HiFiBerry DAC (I²S audio) ---
dtoverlay=hifiberry-dac
dtparam=i2s=on
dtparam=audio=off
```

### After reboot:
```bash
aplay -l
```
Output should include:
```
card 0: sndrpihifiberry [snd_rpi_hifiberry_dac], device 0: HiFiBerry DAC HiFi pcm5102a-hifi-0 []
```

### Test playback:
```bash
speaker-test -D hw:0,0 -c 2 -t sine
```

---

## ⚙️ Fixing “`pa_simple_new()` failed”

This occurred because PulseAudio wasn’t configured for I²S.  
Switching zicPixel to use ALSA fixed it:

```bash
./pixel.arm --output alsa
```

If ALSA is active, you’ll see:
```
[debug] AudioAlsa::open
[info] audio plugin loaded: AudioOutputAlsa
```

---

## 🎚 Encoder Direction Reversal Fix

### Problem
Encoders behaved backward — turning **left increased** values, and **right decreased** them.

### Cause
I²S encoder A/B pin order reversed relative to software logic.

### Fix (software)
Edit `controllers.h`:

```cpp
void encoderHandler(int id, int8_t direction, uint32_t tick)
{
    ViewManager::get().view->onEncoder(id, -direction, tick);
}
```

This inverts encoder direction globally.

### Rebuild
```bash
make pixel
```

---

## 🧠 Optional Configurable Fix

Add:
```cpp
#define ENCODERS_REVERSED 1

void encoderHandler(int id, int8_t direction, uint32_t tick)
{
#if ENCODERS_REVERSED
    direction = -direction;
#endif
    ViewManager::get().view->onEncoder(id, direction, tick);
}
```

Toggle `ENCODERS_REVERSED` to `0` or `1` as needed.

---

## ✅ Final Status

- ✅ **All plugins built successfully**
- ✅ **Audio functional via PCM5102 (I²S)**
- ✅ **Encoders corrected**
- ✅ **Pixel UI and audio engine stable**

---

Generated automatically from a successful zicPixel debug and build session.
