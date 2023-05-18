# sass-hsb-functions

## Description

Graphic design software typically displays colors in the HSB format. However, Sass currently only provides functions to manipulate HSL colors. This project provides some functions that can be used to convert colors from HSB to HSL format and manipulate them.

## Installation

You can install the `sass-hsb-functions` package via npm:

```bash
npm install sass-hsb-functions
```

## Usage

Once installed, you can import the functions in your Sass project:

```scss
@use "sass-hsb-functions/hsb-functions";
// @use "{path-to-node_modules}/sass-hsb-functions/hsb-functions"; // if not using vite, webpack or parcel.

// Use the functions to manipulate HSB colors
$colorHSL: hsb-functions.hsb-to-color(
  305,
  84%,
  95%
); // hsb(305, 84%, 95%) => hsl(305, 88.864142539%, 55.1%)

$colorHSL: hsb-functions.change-color-hsb(
  $color: $colorHSL,
  $saturation: 85%,
  $brightness: 100%,
); // hsb(305, 85%, 100%) => hsl(305, 100%, 57.5%)

$colorHSL: hsb-functions.adjust-color-hsb(
  $color: $colorHSL,
  $saturation: 10%,
); // hsb(305, 95%, 100%) => hsl(305, 100%, 52.5%)
```

## Functions

### hsb-to-color($hue, $saturation, $brightness, $alpha: 1)

Converts an HSB color to HSLA.

- `$hue`: must have either the unit deg or no unit.
- `$saturation`: must be between 0% and 100% (inclusive) Unitless values are also accepted.
- `$brightness`: must be between 0% and 100% (inclusive) Unitless values are also accepted.
- `$alpha`: optional, must be unitless and between 0 and 1 (inclusive).

Returns the equivalent HSLA color value.

### change-color-hsb($color, $saturation: null, $brightness: null)

Sets saturation and/or brightness properties (HSB) of $color to new values. It is similar to the built-in  `change-color()` function on Sass.

- `$color`: valid SASS color value.
- `$saturation`: must be between 0% and 100% (inclusive) Unitless values are also accepted.
- `$brightness`: must be between 0% and 100% (inclusive) Unitless values are also accepted.

Returns the equivalent HSLA color value.

### adjust-color-hsb($color, $saturation: 0%, $brightness: 0%)

Increases or decreases saturation and/or brightness properties (HSB) of $color by fixed amounts. It is similar to the built-in `adjust-color()` function on Sass.

- `$color`: valid SASS color value.
- `$saturation`: must be between 0% and 100% (inclusive) Unitless values are also accepted.
- `$brightness`: must be between 0% and 100% (inclusive) Unitless values are also accepted.

Returns the equivalent HSLA color value.

## Contributing

Contributions are welcome! If you have any suggestions, bug reports, or feature requests, please open an issue on the [GitHub repository](https://github.com/viktor992/sass-hsb-functions).

## License

This project is licensed under the [MIT License](LICENSE).
