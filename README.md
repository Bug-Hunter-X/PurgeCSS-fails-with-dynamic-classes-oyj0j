# PurgeCSS issue with dynamic Tailwind classes
This repository demonstrates a bug where PurgeCSS, used with Tailwind CSS, fails to remove unused styles when class names are generated dynamically using JavaScript.  The issue occurs because the class names are not known at compile time.

## Setup

1. Clone the repository
2. Run `npm install`
3. Run `npm run build`

## Expected Behavior

PurgeCSS should remove any unused Tailwind CSS classes from the final CSS file.  The output CSS should be smaller.

## Actual Behavior

PurgeCSS includes all Tailwind CSS classes, even those that are not used in the application.

## Solution

The provided solution utilizes the `@apply` directive which allows the application of Tailwind utilities directly to your HTML.  This approach eliminates the need for dynamic class generation which removes the conflict with PurgeCSS.