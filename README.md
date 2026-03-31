# AngleFade

UE 5.6 project for testing angle-based ceiling fade behavior.

## Current Setup

- Project: `Angle_Test.uproject`
- Engine: Unreal Engine 5.6
- Default working level: `Content/_Angle/Map/L_Angle.umap`
- Main ceiling material: `Content/_Angle/Mesh/M_Ceiling.uasset`

## Ceiling Fade Material

`M_Ceiling` is configured to fade based on the camera view angle.

- Lower view angles keep the original ceiling texture visible.
- Higher view angles fade the ceiling toward transparency.
- The fade is driven inside `M_Ceiling` without creating a separate material instance.

Material tuning parameters:

- `AngleFadeStartDot = -0.05`
- `AngleFadeEndDot = 0.2`

Current opacity flow in the material graph:

`CameraVector -> Dot(Z Up) -> Remap(Start/End) -> Clamp -> OneMinus -> Opacity`

## Demo

Angle-based ceiling fade preview:

![AngleFade ceiling fade demo](docs/media/anglefade-demo.gif)

## Git LFS

Git LFS is enabled for large Unreal and content assets, including:

- `*.uasset`
- `*.umap`
- `*.fbx`
- `*.png`
- `*.jpg`
- `*.jpeg`
- `*.tga`
- `*.psd`
- `*.wav`
- `*.mp3`
- `*.mp4`
- `*.mov`
- `*.avi`
- `*.exr`
- `*.blend`
- `*.zip`

## Repo Notes

- `DerivedDataCache/`, `Intermediate/`, and `Saved/` are ignored.
- `Plugins/UE5AIAssistant/UE5AIAssistant.uplugin` is included so the editor control bridge can be enabled in this project.
