# AsyncStorage Data Race Condition in React Native

This repository demonstrates a common error encountered when using AsyncStorage in React Native: attempting to access data before it has been fully retrieved. This leads to undefined values and potential app crashes.

## Problem

AsyncStorage's getItem method is asynchronous. Directly using its result before the Promise resolves yields undefined, causing errors in subsequent operations. The example illustrates this with a simple key-value pair retrieval.

## Solution

The solution uses the .then() method to correctly handle the asynchronous nature of AsyncStorage.getItem(), ensuring the value is accessed only after the Promise fulfills. This approach prevents the data race condition and ensures the app functions correctly.

## How to Reproduce

1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install` to install the necessary dependencies.
4. Run `npx react-native run-android` (or `npx react-native run-ios`) to start the app.
5. Observe the console output.  The bug will show undefined, while the solution will display the correct value.