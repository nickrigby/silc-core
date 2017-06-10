# silc core [![Build Status](https://travis-ci.org/nickrigby/silc-core.svg?branch=master)](https://travis-ci.org/nickrigby/silc-core) [![npm version](https://badge.fury.io/js/silc-core.svg)](https://badge.fury.io/js/silc-core)

The core module contains a number of SASS variables/mixins/functions, and a JavaScript class for the silc framework.

## SASS functions

### em
Converts a pixel value into its `em` equivalent. Accepts a second "context" parameter, which is the context value to base the calculation on. The context parameter defaults to the value of `@silc-core--font-size`, which by default is `16px`.

```scss
em(16); // Returns 1em
em(16, 32); // Return 2em
```

### rem
Converts a pixel value into its `rem` equivalent. The context for `rem` calculations is the root (html) element font size, which defaults to the value of `@silc-core--font-size`.

```scss
rem(25); // Returns 1.5rem
```

### strip-unit
Strips units from a passed in string.

```scss
strip-unit(16px); // Returns 16
```

## SASS mixins

### media
Creates a media query based on a passed in breakpoint name, defined in `$silc-core--breakpoints`.

```scss
@include media('large') {
    font-size: rem(20);
}
```

## SASS variables
A number of [SASS variables](src/scss/_variables.scss) are available to override. One particular variable to pay attention to is the `$silc-core--breakpoints` variable. The breakpoints variable allows you to create your own named breakpoints, which will then be used when using other silc modules like [silc-grid](https://github.com/nickrigby/silc-grid).

## JavaScript class
The `SilcCore` class adds a `js` class to the body element, which can then be used to progressively enhance your styles.
