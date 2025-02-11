# Expo Camera API: accessing cameraRef before initialization

This repository demonstrates a common error when using the Expo Camera API: attempting to access the `cameraRef` object before the camera has fully initialized.  This can lead to unexpected behavior, crashes, or null pointer exceptions. The solution involves using the `onCameraReady` callback to ensure the camera is ready before accessing it.

## Bug Description:

The `Camera` component from Expo's `expo-camera` package initializes asynchronously. If you attempt to access properties or functions of the `cameraRef` (e.g., taking a picture) before the camera is ready, you might encounter errors because `cameraRef` will be `null`.

## Solution:

Use the `onCameraReady` callback provided by the `Camera` component. This callback is triggered only after the camera has been successfully initialized, ensuring safe access to the `cameraRef` object.

## How to reproduce the bug:

1. Clone this repository.
2. Run `npm install`.
3. Run `expo start`.
4. Observe the console for errors.

## How to fix the bug:

Refer to `bugSolution.js` for the corrected code.