# React Native Dimensions API Returns 0 Width and Height on Android

This repository demonstrates a common issue in React Native where the `Dimensions` API returns incorrect (often 0) values for screen width and height, primarily on Android devices. This happens frequently during the initial render or when the orientation changes because the layout hasn't fully calculated yet.

The `bug.js` file shows the problematic code, while `bugSolution.js` provides a solution using `onLayout` to ensure accurate dimensions.

## How to reproduce

1. Clone the repository.
2. Run the app on an Android emulator or device.
3. Observe the initially logged width and height; they will likely be 0.
4. Rotate the device to trigger an orientation change.
5. Observe the logged dimensions again; they might be incorrect or still 0 initially after rotation.

## Solution

The solution involves using the `onLayout` event handler provided by the `View` component.  This event will be fired once the layout of the view has been completed, ensuring accurate `width` and `height` values. See `bugSolution.js` for implementation details.