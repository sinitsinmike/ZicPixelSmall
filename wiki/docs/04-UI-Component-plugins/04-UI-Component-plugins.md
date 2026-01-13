


## ScrollGroup

ScrollGroup is a container that scroll the grouped component together.


- `CONTAINER_BACKGROUND_COLOR: color` is the background color of the component.

- `SCROLL_TO_CENTER: true/false` scroll to center (default: false).

- `SCROLL_OFFSET: 100` set the where group component start to scroll. By default 70% from container height.

## Visibility

Visibility is a container that show/hide the components for a given group index.


- `CONTAINER_BACKGROUND_COLOR: color` is the background color of the component.

- `VISIBILITY_GROUP: 0` the group index to show/hide the components.

- `VISIBILITY_CONTEXT: index SHOW_WHEN/SHOW_WHEN_NOT/SHOW_WHEN_OVER/SHOW_WHEN_UNDER value` the context index to show/hide the components for a given value.



## Icons

List of icon used in plugin component:


- `&icon::backspace`

- `&icon::backspace::filled`

- `&icon::play`

- `&icon::play::filled`

- `&icon::stop`

- `&icon::stop::filled`

- `&icon::pause`

- `&icon::pause::filled`

- `&icon::arrowUp`

- `&icon::arrowUp::filled`

- `&icon::arrowDown`

- `&icon::arrowDown::filled`

- `&icon::arrowLeft`

- `&icon::arrowLeft::filled`

- `&icon::arrowRight`

- `&icon::arrowRight::filled`

- `&icon::musicNote`

- `&icon::musicNote::pixelated`

- `&icon::tape`

- `&icon::toggle`

- `&icon::toggle::rect`

- `&icon::trash`

- `&empty`

## KeypadLayout

Some components might want to use a keypad layout.


- `KEYMAP: controllerName key action [param] [color]` Map an action to a controller key. Use `Keyboard` as `controllerName` to use computer keyboard. Use 'A' to 'Z' and '0' to '9' to use computer keyboard. Other key should use scancode number without quotes.


Pixel Components

ZicBox load UI plugin, called component, and organize them by views. Those components have access to each others and to the audio plugins.


## GraphComponent

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/adsr.png" />

Show a representation of the ADSR envdelop.


**Config**:

- `PLUGIN: plugin_name` set plugin target

- `OUTLINE: true/false` is if the envelop should be outlined (default: true).

- `FILLED: true/false` is if the envelop should be filled (default: true).

- `BACKGROUND_COLOR: color` is the background color of the component.

- `FILL_COLOR: color` is the color of the envelop.

- `OUTLINE_COLOR: color` is the color of the envelop outline.

- `TEXT_COLOR1: color` is the color of the value.

- `TEXT_COLOR2: color` is the color of the unit.

- `INACTIVE_COLOR_RATIO: 0.0 - 1.0` is the ratio of darkness for the inactive color (default: 0.5).

- `ENCODERS: A_encoder_id D_encoder_id S_encoder_id R_encoder_id` is the id of the encoder to update given value.

- `VALUES: A_value D_value S_value R_value` are the values id for the encoders and data point.

## Clips

Clips components to draw a rectangle.


**Config**:

- `GROUP_ALL: group` is the group to change clips for all tracks.

- `BACKGROUND_COLOR: color` is the background color of the component.

- `FOREGROUND_COLOR: color` is the foreground color of the component.

- `TEXT_COLOR: color` is the text color of the component.

- `COLOR: color` is the foreground color of the component.

- `PLUGIN: plugin_name` set plugin target for serializer

- `VISIBLE_COUNT: number` set the number of visible clips.

- `SEQ_PLUGIN: plugin_name` set plugin target for sequencer.

## Drum envelop

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/DrumEnvelop.png" />

Show a representation of a drum envelop (envelop with relative time and modulation, without sustain).


**Config**:

- `PLUGIN: plugin_name` set plugin target

- `ENVELOP_DATA_ID: id` is the id of the envelope data.

- `STEP_DATA_ID: id` is the data id to get/set the current step/phase to edit.

- `TIME_DATA_ID: id` is the data id to get/set the step to time.

- `MOD_DATA_ID: id` is the data id to get/set the step to mod.

- `OUTLINE: true/false` is if the envelop should be outlined (default: true).

- `FILLED: true/false` is if the envelop should be filled (default: true).

- `ENCODER_PHASE: id` is the id of the encoder to control the phase.

- `ENCODER_TIME: id` is the id of the encoder to control the time.

- `RENDER_TITLE_ON_TOP: true/false` is if the title should be rendered on top (default: true).

- `ENCODER_MODULATION: id` is the id of the encoder to control the modulation.

- `BACKGROUND_COLOR: color` is the background color of the component.

- `FILL_COLOR: color` is the color of the envelop.

- `OUTLINE_COLOR: color` is the color of the envelop outline.

- `TEXT_COLOR: color` is the color of the text.

- `CURSOR_COLOR: color` is the color of the cursor.

- `INACTIVE_COLOR_RATIO: 0.0 - 1.0` is the ratio of darkness for the inactive color (default: 0.5).

## FmAlgo

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/fm/algo1.png" />
<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/fm/algo2.png" />
<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/fm/algo3.png" />
<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/fm/algo4.png" />
<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/fm/algo5.png" />
<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/fm/algo6.png" />
<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/fm/algo7.png" />
<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/fm/algo8.png" />
<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/fm/algo9.png" />
<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/fm/algo10.png" />
<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/fm/algo11.png" />
<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/fm/algo12.png" />

Show FM algorithm and change them. The filled square are the carrier where audio is outputted and the not filled square are the operators modulating the frequency.


- `BACKGROUND_COLOR: #333333` set the background color.

- `VALUE: pluginName keyName` is used to set the value to control.

- `ENCODER_ID: 0` is used to set the encoder id that will interract with this component.

- `DATA_ID: 0` is used to set the data id that will return the current algorithm layout.

- `TEXT_COLOR: #FFFFFF` set the text color.

- `BORDER_COLOR: #888888` set the border color.

## GraphEncoderComponent

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/graphEncoder.png" />

Show a representation of data points and provide a way to control them.


**Config**:

- `PLUGIN: plugin_name` set plugin target

- `OUTLINE: true/false` is if the envelop should be outlined (default: true).

- `FILLED: true/false` is if the envelop should be filled (default: true).

- `BACKGROUND_COLOR: color` is the background color of the component.

- `FILL_COLOR: color` is the color of the envelop.

- `OUTLINE_COLOR: color` is the color of the envelop outline.

- `TEXT_COLOR1: color` is the color of the value.

- `TEXT_COLOR2: color` is the color of the unit.

- `INACTIVE_COLOR_RATIO: 0.0 - 1.0` is the ratio of darkness for the inactive color (default: 0.5).

- `DATA_ID: data_id` is the data id to get the shape/graph to draw.

- `ENCODER: encoder_id value [string]` is the id of the encoder to update given value, e.g. `ENCODER: 0 LEVEL`. Set `string` to force using string rendering.

- `IS_ARRAY: true/false` is if the data is an array.

## HiddenValue

Hidden value component is used to change a value without showing it.


- `VALUE: pluginName keyName` is used to set the value to control

- `ENCODER_ID: 0` is used to set the encoder id that will interract with this component

- `INVERTED: true` is used to invert the encoder direction

## Keyboard

Keyboard components to display keyboard.


**Config**:

- `REDIRECT_VIEW: viewName` is the view to return when the edit is finished.

- `DONE_DATA: plugin data_id` is the data id to return when the edit is done.

- `BACKGROUND_COLOR: color` is the color of the background.

- `TEXT_COLOR: color` is the color of the text.

- `SELECTION_COLOR: color` is the color of the selection.

- `ITEM_BACKGROUND: color` is the color of the item background.

## KnobValue

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/KnobValue.png" />

KnobValue is used to display current audio plugin value for a given parameter.


- `VALUE: pluginName keyName` is used to set the value to control

- `ENCODER_ID: 0` is used to set the encoder id that will interract with this component

- `TYPE: TWO_SIDED` is used to set the encoder type
    - `TYPE: TWO_SIDED` when there is a centered value like PAN and you want to show both side value: 20%|80%


- `LABEL: custom_label` overwrite the value label

- `COLOR: #3791a1` set the ring color

- `BACKGROUND_COLOR: #000000` set the background color

- `TEXT_COLOR: #ffffff` set the text color

- `FLOAT_PRECISION: 2` set how many digits after the decimal point (by default none)

- `USE_SECOND_COLOR: value` set the percentage value when `BAR2_COLOR` should be used instead of `BAR_COLOR`, e.g. 0.5 will switch at 50%

- `SHOW_VALUE: true` show value (default true)

- `SHOW_UNIT: true` show unit (default true)

- `FONT_UNIT_SIZE: 12` set the unit font size

- `FONT_VALUE_SIZE: 12` set the value font size

- `FONT_TITLE_SIZE: 12` set the title font size

- `STRING_VALUE_REPLACE_TITLE: true` instead to show string value in knob, show under the knob. Can be useful for long string value.

## List

List components to display list of items.


**Config**:

- `REDIRECT_VIEW: viewName` is the view to return when the edit is finished.

- `ADD_ITEM: text` is the item to add to the list.

- `PLUGIN: plugin` is the plugin to use to make action on the list.

- `BACKGROUND_COLOR: color` is the color of the background.

- `TEXT_COLOR: color` is the color of the text.

- `SELECTION_COLOR: color` is the color of the selection.

- `ITEM_BACKGROUND: color` is the color of the item background.

## Macro envelop

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/MacroEnvelop.png" />

Show a representation of a macro envelop (envelop with relative time and modulation, without sustain).


**Config**:

- `PLUGIN: plugin_name` set plugin target

- `ENVELOP_DATA_ID: id` is the id of the envelope data.

- `OUTLINE: true/false` is if the envelop should be outlined (default: true).

- `FILLED: true/false` is if the envelop should be filled (default: true).

- `ENCODER_PHASE: mode macro1 macro2 macro3` is the id of the encoders.

- `BACKGROUND_COLOR: color` is the background color of the component.

- `FILL_COLOR: color` is the color of the envelop.

- `OUTLINE_COLOR: color` is the color of the envelop outline.

- `TEXT_COLOR: color` is the color of the text.

- `CURSOR_COLOR: color` is the color of the cursor.

- `INACTIVE_COLOR_RATIO: 0.0 - 1.0` is the ratio of darkness for the inactive color (default: 0.5).

## Rect

Rect components to draw a rectangle.


**Config**:

- `COLOR: color` is the color of the component.

- `FILLED: true/false` is if the rectangle should be filled (default: true).

## Sample

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/pixel/Sample.png" />

Sample is used to display an audio sample, sustain position, and start/end position.
The little green dot are the current playing positions of the sample.


- `BACKGROUND_COLOR: #000000` set background color

- `OVERLAY_COLOR:#a2beb8` set overlay color

- `OVERLAY_EDGE_COLOR:#a6b1ab` set overlay edge color

- `LOOP_START_COLOR:#548ebe` set loop start point color

- `LOOP_END_COLOR:#548ebe` set loop end point color

- `LOOP_POINTS_COLOR:#548ebe` set loop end and start point color

- `KEYS: BROWSER START END SUSTAIN LENGTH` set the key parameter to use from plugin

- `PLUGIN: pluginName bufferDataId [sampleIndexDataId]` set the plugin to use from plugin

## SampleEditor

SampleEditor components to edit sample...


**Config**:

- `BACKGROUND_COLOR: background` is the color of the background of the component.

- `TAPE_FOLDER` set samples folder path.

- `FILENAME: filename` to set filename. By default it is `track`.

- `BEAT_ENCODER: encoderId` to set the encoder id to define the beat where to start to display the waveform (default: 0).

- `TRACK_ENCODER: encoderId` to set the encoder id to define the track number to record (default: 2).

- `BPM_VALUE: plugin key` to get the bpm value.

- `TAPE_PLUGIN: plugin [playStopDataId] [syncDataId]` to set the play/stop data id of the tape plugin.

## SeqBar

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/seqBar.png" />


**Config**:

- `SEQ_PLUGIN: plugin_name [get_steps_data_id]` set plugin target for sequencer

- `NAME_PLUGIN: plugin_name value_key` set the plugin target to be used for the name.

- `NAME: name` set the name of the component.

- `VOLUME_PLUGIN: plugin_name value_key` is used for the volume bar (but can be any else).

- `SELECT_ITEM_CONTEXT: context_id` is the context id for the selected item (default is 10).

- `BACKGROUND_COLOR: color` is the background color of the component.

- `TEXT_COLOR: color` is the color of the text.

- `FOREGROUND_COLOR: color` is the foreground color.

- `ACTIVE_STEP_COLOR: color` is the color of the active step.

- `NAME_COLOR: color` is the color of the name.

- `SELECTION_COLOR: color` is the selection color.

## SeqProgressBarComponent

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/seqProgressBar.png" />


**Config**:

- `SEQ_PLUGIN: plugin_name [track]` set plugin target for sequencer

- `VOLUME_PLUGIN: plugin_name value_key` is used for the volume bar (but can be any else).

- `BACKGROUND_COLOR: color` is the background color of the component.

- `FOREGROUND_COLOR: color` is the foreground color.

- `ACTIVE_COLOR: color` is the color of the active step.

- `SELECTION_COLOR: color` is the selection color.

- `SHOW_STEPS: true` show sequencer step value (default: false).

## SeqSynthBar

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/seqSynthBar.png" />


**Config**:

- `SEQ_PLUGIN: plugin_name [get_steps_data_id]` set plugin target for sequencer

- `NAME_PLUGIN: plugin_name value_key` set the plugin target to be used for the name.

- `NAME: name` set the name of the component.

- `VOLUME_PLUGIN: plugin_name value_key` is used for the volume bar (but can be any else).

- `SELECT_MENU_CONTEXT: context_id` is the context id for the selected synth menu (default is 11).

- `SELECT_ITEM_CONTEXT: context_id` is the context id for the selected item (default is 10).

- `ITEMS: name name name name name` is the name of the items.

- `BACKGROUND_COLOR: color` is the background color of the component.

- `TEXT_COLOR: color` is the color of the text.

- `FOREGROUND_COLOR: color` is the foreground color.

- `ACTIVE_STEP_COLOR: color` is the color of the active step.

- `NAME_COLOR: color` is the color of the name.

- `SELECTION_COLOR: color` is the selection color.

## Spectrogram

Spectrogram components to display audio spectrogram.


**Config**:

- `BACKGROUND_COLOR: color` is the background color of the component.

- `WAVE_COLOR: color` is the color of the wave.

- `WAVE_COLOR_OUT: color` is the color of the wave.

- `WAVE_COLOR_MIDDLE: color` is the color of the wave.

- `WAVE_COLOR_IN: color` is the color of the wave.

- `TEXT_COLOR: color` is the color of the text.

- `TEXT: text` is the text to display.

- `MIRROR: false` mirror the waveform horizontally (default: true).

- `RAW_BUFFER: true` display the raw buffer (default: false).

## StepEdit2

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/stepEdit2.png" />

StepEdit component is used to edit a step value.


**Config**:

- `DATA: plugin_name get_step_data_id step_index [sequence_data_id] [counter_data_id]` set plugin target

- `ENCODERS: encoder_id1 encoder_id2 encoder_id3` is the id of the encoder to update step value. This component use 3 encoders. In standard view, it will change note, velocity and length. In shift view, it will change note, condition and motion.

- `SHIFT_CONTEXT_INDEX: index` is the index of the context (default: 100).

- `BACKGROUND_COLOR: color` is the background color of the component.

- `PLAYING_COLOR: color` is the color of actual playing step.

- `NOTE_COLOR: color` is the color of the note.

- `NOTE2_COLOR: color` is the color of the note.

- `TEXT_COLOR: color` is the color of the text.

- `BAR_COLOR: color` is the color of the velocity bar.

- `TEXT_MOTION1_COLOR: color` is the first color of the motion text.

- `TEXT_MOTION2_COLOR: color` is the second color of the motion text.

- `SELECTED_COLOR: color` is the color of the selected step.

## StepEdit

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/stepEdit.png" />

StepEdit component is used to edit a step value.


**Config**:

- `GROUP_RANGE: index1 index2` is the index of the first and last group for selection.

- `DATA: plugin_name data_id step_index` set plugin target

- `COUNTER_DATA_ID: data_id` is the data id to show active step.

- `SEQUENCE_DATA_ID: data_id` is the data id to show if the sequence is playing.

- `ENCODERS: encoder_id1 encoder_id2 encoder_id3` is the id of the encoder to update step value. This component use 3 encoders. In standard view, it will change note, velocity and length. In shift view, it will change note, condition and motion.

- `SHIFT_MODE: 255` set the index of the context variable bank to use to switch between velocity/length and condition/motion. There is 255 context variable banks share within the whole app.

- `GLOBAL_SHIFT: 0` set the index of the context variable bank to detect gloabl shift value.

- `BACKGROUND_COLOR: color` is the background color of the component.

- `TEXT_COLOR: color` is the color of the text.

- `BAR_COLOR: color` is the color of the velocity bar.

- `BAR_BACKGROUND_COLOR: color` is the color of the velocity bar background.

- `TEXT_MOTION1_COLOR: color` is the first color of the motion text.

- `TEXT_MOTION2_COLOR: color` is the second color of the motion text.

## StepEditDrum

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/stepEditDrum.png" />

StepEditDrum component is used to edit a step value for drums.


**Config**:

- `DATA: plugin_name get_step_data_id step_index [sequence_data_id] [counter_data_id]` set plugin target

- `ENCODERS: encoder_id1 encoder_id2 encoder_id3 encoder_id4` is the id of the encoder to update step value.

- `BACKGROUND_COLOR: color` is the background color of the component.

- `PLAYING_COLOR: color` is the color of actual playing step.

- `NOTE_COLOR: color` is the color of the note.

- `NOTE2_COLOR: color` is the color of the note.

- `TEXT_COLOR: color` is the color of the text.

- `BAR_COLOR: color` is the color of the velocity bar.

- `TEXT_MOTION1_COLOR: color` is the first color of the motion text.

- `TEXT_MOTION2_COLOR: color` is the second color of the motion text.

- `SELECTED_COLOR: color` is the color of the selected step.

## StepEditMono

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/stepEditSmall.png" />

StepEditMono component is used to edit a step value using only one knob.


**Config**:

- `DATA: plugin_name get_step_data_id step_index [sequence_data_id] [counter_data_id]` set plugin target

- `ENCODER: encoder_id` is the id of the encoder to update step value.

- `BACKGROUND_COLOR: color` is the background color of the component.

- `PLAYING_COLOR: color` is the color of actual playing step.

- `SHOW_PLAYING_STEP: true` is to enable the task to show actual playing step.

- `ON_COLOR: color` is the color of the note.

- `OFF_COLOR: color` is the color of the text.

- `CONDITION_COLOR: color` is the color of the text.

- `SELECTED_COLOR: color` is the color of the selected step.

## StepEditSample

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/stepEditSample.png" />

StepEditSample component is used to edit a step value for samples.


**Config**:

- `DATA: plugin_name step_index [get_step_data_id]` set plugin target

- `ENCODERS: encoder_id1 encoder_id2 encoder_id3 encoder_id4` is the id of the encoder to update step value.

- `BACKGROUND_COLOR: color` is the background color of the component.

- `PLAYING_COLOR: color` is the color of actual playing step.

- `FILE_COLOR: color` is the color of the file.

- `NOTE2_COLOR: color` is the color of the note.

- `TEXT_COLOR: color` is the color of the text.

- `BAR_COLOR: color` is the color of the velocity bar.

- `TEXT_MOTION1_COLOR: color` is the first color of the motion text.

- `TEXT_MOTION2_COLOR: color` is the second color of the motion text.

- `SELECTED_COLOR: color` is the color of the selected step.

## Tape

Tape components to draw a rectangle.


**Config**:

- `BACKGROUND_COLOR: background` is the color of the background of the component.

- `TAPE_FOLDER` set samples folder path.

- `FILENAME: filename` to set filename. By default it is `track`.

- `BEAT_ENCODER: encoderId` to set the encoder id to define the beat where to start to display the waveform (default: 0).

- `TRACK_ENCODER: encoderId` to set the encoder id to define the track number to record (default: 2).

- `BPM_VALUE: plugin key` to get the bpm value.

- `TAPE_PLUGIN: plugin [playStopDataId] [syncDataId]` to set the play/stop data id of the tape plugin.

## Rect

Rect components to draw a rectangle.


**Config**:

- `BACKGROUND_COLOR: color` is the color of the component.

## Text

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/text.png" />

Text component is used to display text.


**Config**:

- `TEXT: text` is the text of the component.

- `CENTERED: true/false` is if the text should be centered (default: false).

- `FONT_SIZE: size` is the font size of the component.

- `FONT: font` is the font of the component.

- `FONT_HEIGHT: height` is the font height of the component.

- `BACKGROUND_COLOR: color` is the background color of the component.

- `COLOR: color` is the color of the component.

## TextGrid

TextGrid components to display text in a table.


**Config**:

- `ROW: text text text text text` is the text to add in row.

- `VISIBILITY_CONTEXT: index SHOW_WHEN/SHOW_WHEN_NOT/SHOW_WHEN_OVER/SHOW_WHEN_UNDER value` the context index to show/hide the components for a given value.

- `VISIBILITY_GROUP: SHOW_WHEN/SHOW_WHEN_NOT/SHOW_WHEN_OVER/SHOW_WHEN_UNDER group_id` the group index to show/hide the components.

- `BACKGROUND_COLOR: color` is the color of the background.

- `TEXT_COLOR: color` is the color of the text.

- `TEXT_COLOR2: color` is the color of the text.

- `ITEM_BACKGROUND: color` is the color of the item background.

## Value

<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/value.png" />
<img src="https://raw.githubusercontent.com/apiel/zicBox/main/plugins/components/Pixel/value2.png" />

Value component is used to display an audio plugin value.


**Config**:

- `VALUE: pluginName keyName` is used to set the value to control

- `ENCODER_ID: 0` is used to set the encoder id that will interract with this component

- `FLOAT_PRECISION: 2` set how many digits after the decimal point (by default none)

- `USE_STRING_VALUE: true` use the string value instead of the floating point one (default: false)

- `BAR_HEIGHT: 2` set the bar height (default: 2)

- `BAR_BG_HEIGHT: 1` set the bar background height (default: 1)

- `VERTICAL_ALIGN_CENTER: true` set the text vertical alignment to center (default: false)

- `SHOW_VALUE: true` shows the value (default: true)

- `SHOW_UNIT: true` shows the unit (default: true)

- `SHOW_LABEL: true` shows the label (default: true)

- `SHOW_LABEL_OVER_VALUE: 4` shows the label over the value, 4 px from the top of the component (default: -1) `

- `LABEL_OVER_VALUE_X: 0` set the distance from the left of the component where the label will be placed. If -1 it is centered (default: -1)

- `LABEL: label` is the label of the component.

- `VALUE_FONT_SIZE: size` is the font size of the component.

- `LABEL_FONT_SIZE: size` is the font size of the component.

- `UNIT_FONT_SIZE: size` is the font size of the component.

- `FONT: font` is the font of the component.

- `VALUE_FONT_HEIGHT: 16` is the font height of the value.

- `BACKGROUND_COLOR: color` is the background color of the component.

- `VALUE_COLOR: color` is the color of the value.

- `BAR_COLOR: color` is the color of the bar.

- `UNIT_COLOR: color` is the color of the unit.

- `LABEL_COLOR: color` is the color of the label.

## Workspaces

Workspaces components show the list of available workspaces.


**Config**:

- `PLUGIN: plugin` is the plugin to use to make action on the list.

- `WORKSPACE_FOLDER: workspaceFolder` to set workspace folder. By default it is `workspaces`.

- `BADGE_COLOR: badgeColor` to set badge color. By default it is `#23a123`.

- `ERROR_COLOR: errorColor` to set error color. By default it is `#ad6363`.