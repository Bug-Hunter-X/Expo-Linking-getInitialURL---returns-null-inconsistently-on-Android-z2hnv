# Expo Linking.getInitialURL() Inconsistencies on Android

This repository demonstrates a bug where `Linking.getInitialURL()` in Expo inconsistently returns `null` on Android devices, even when a deep link is successfully opened. This can lead to unexpected application behavior as the app fails to handle the intended deep link.

## Reproducing the Bug

1. Clone this repository.
2. Install dependencies: `npm install` or `yarn install`
3. Run the app on an Android emulator or device.
4. Open a deep link (as defined in the `app.json` file).
5. Observe the console output; it might show `null` despite a successful deep link. 

## Potential Causes

The root cause may involve timing issues or interactions between Expo's internal mechanisms and Android's deep link handling.  Further investigation into Expo's source code is recommended for a definitive explanation. 

## Proposed Solution

A robust solution is presented that involves retrying `getInitialURL()` to handle temporary inconsistencies. This approach mitigates the issues by giving the system enough time to resolve the initial URL before proceeding.