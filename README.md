# Figma Tokens for TailwindCSS and DaisyUI

This repository contains the files with the configuration of the **Design Tokens** for [TailwindCSS](https://tailwindcss.com/) and [DaisyUI](https://daisyui.com/) that can be used with [Tokens Studio for Figma](https://tokens.studio) (*Figma Tokens*).

## What are Design Tokens?

Design Tokens are a way of abstracting design values into reusable, single sources of truth represented as data, that ensure systematically unified and cohesive product experiences. These values can include colors, typography, spacing, and more. By using Design Tokens, you can create a unified and consistent design system.


## How to Use These Design Tokens

To use these Design Tokens, you need to have the [Tokens Studio for Figma](https://tokens.studio) (Figma Tokens) plugin installed in your Figma account. Once installed, you can import the JSON files into your Tokens Studio and use them to create your design system.

These files were made with the standard version of the plugin without the ***Advanced themes*** or ***Compositions*** options that require a Pro account.

The files are divided into diferents sets, although in this way it is not possible to use ***Multi File Sync*** (Pro).

## Files

This repository contains the following files:

- [core.tw.figmaTokens.json](https://github.com/ernestoruperez/eo_design-tokens/blob/master/tailwind/core.tw.figmaTokens.json): A JSON file containing the global configuration of the Design Tokens for TailwindCSS v.3.
- [light.daisy.json](https://github.com/ernestoruperez/eo_design-tokens/blob/master/daisy/light.daisy.figmaTokens.json) and [dark.daisy.json](https://github.com/ernestoruperez/eo_design-tokens/blob/master/daisy/light.daisy.figmaTokens.json): A JSON file containing the configuration of the Design Tokens for DaisyUI with the variables of the default light and dark theme.

## Tokens for TailwindCSS

1. **Spacing**: **`spacing`**

    - Same as TW, the spacing scale is inherited by the `padding`, `margin`, `widht`,`height`, `maxHeight`, `gap`, `inset`, and `space` using this token reference as value.
    - To build the spacing tokens, it's constructed using this formula: `{fontSize.base} * (value in rem)` without *rem/px* value. *More information about using Math: [Link](https://docs.tokens.studio/tokens/using-math)*.
    
1. **Typography**: **`typography`**

    - Values: `fontFamily`, `fontWeight`, `lineHeight`, `fontSize`, `letterSpacing`, `paragraphSpacing`, `paragraphIndent`, `textDecoration`, `textTransform`. 

1. **Color**: `colors`

    - In addition to the 5 gray palettes, there's an extra one called `default-gray` that you can use as a token reference and quickly replace the main palette. `{colors.default-gray.400} = {color.slate.400}` 
    - The `primary`, `secondary`, `status` or `base` tokens are being used in the DaisyUI file.
    
1. **Sizing**: **`sizing`** and **`screens`**

    - `sizing` use the token references `spacing` for width and height values.

1. **Border Radius**: **`borderRadius`**

1. **Border Width**: **`borderWidth`**

1. **Border**: **`borderStyle`**

1. **Opacity**: **`opacity`**

1. **Box Shadow**: **`boxShadow`**

1. **Font Family**: **`fontFamily`**
    
    - The `fontFamily.sans` has the value `"SF Pro, system-ui, sans-serif"`. It uses the Mac system font [SF Pro](https://developer.apple.com/fonts/) and it doesn't use the allowed `system-ui` by Figma, in order to use the variable typography values.  
    - Also, you can remove `SF Pro` to use `system-ui`, replace it with the variable typography `Segoe UI` from Windows, or use any other typography.
    
1. **Font Weight**: **`FontWeight`**

    - The default TW configuration includes the **`fontWeights`**: `thin`, `extralight`, `light`, `normal`, `medium`, `semibold`, `bold`, `extrabold`, and `black`.
    - They have been expanded with the **`fontStretch`** no available in TW: `default`, `italic`, `compressed`, `condensed`, and `expanded` from the SF Pro variable font.

1. **Line Height**: **`lineHeight`**

1. **Font Size**: **`fontSize`**

    - Calculated `fontSize` tokens based on `{fontSize.base}`.

1. **Letter Spacing**: **`letterSpacing`**

1. **Paragraph Spacing**: **`paragraphSpacing`**

1. **Text Case**: **`textTransform`**

1. **Text Decoration**: **`textDecoration`**

1. **Dimension**: **`dimension`**

    - `dimension` use the token references `spacing`.
    - This token is introduced in order to support the upcoming W3C format: [Link](https://second-editors-draft.tr.designtokens.org/format/#dimension)

### Tailwind defaultConfig

Full default config JSON for Tailwind 3.2.7: [Link](https://github.com/tailwindlabs/tailwindcss/blob/master/stubs/defaultConfig.stub.js)

## Tokens for DaisyUI

1. **Color**: **`d_colors`**: `d_colors.semantic`, `d_colors.base` and `d_colors.status`.

1. **Border Radius**: **`d_borderRadius`**

1. **Border Width**: **`d_borderWidth`**

1. **Text Case**: **`d_textTransform`**

1. **Other**: **`d_other.buttons`**

### Themes

The light and dark themes use a prefix to differentiate themselves from TW since they use the same reference. However, both of these themes use the same `prefix=d` to show the theme change when using `Apply to selection` and changing the active set.

### DaisyUI variables and Token references.

#### Required

```
[data-theme="light"] {
  color-scheme: light;
  --p: {d_colors.semantic.primary};
  --s: {d_colors.semantic.secondary};
  --a: {d_colors.semantic.accent};
  --n: {d_colors.base.neutral};
  --b1: {d_colors.base.base-100};
}
```

#### Optional

```
[data-theme="light"] {
  color-scheme: light;
  --in: {d_colors.status.info};
  --inc: {d_colors.status.info-content};
  --su: {d_colors.status.success};
  --suc: {d_colors.status.success-content};
  --wa: {d_colors.status.warning};
  --wac: {d_colors.status.warning-content};
  --er: {d_colors.status.error};
  --erc: {d_colors.status.error-content};
  --rounded-box: {d_borderRadius.rounded-box};
  --rounded-btn: {d_borderRadius.rounded-btn};
  --rounded-badge: {d_borderRadius.rounded-badge};
  --animation-btn: ;
  --animation-input: ;
  --btn-text-case: {d_textTransform.btn-text-case};
  --btn-focus-scale: {d_others.btn-focus-scale};
  --border-btn: {d_borderWidth.border-btn};
  --tab-border: {d_borderWidth.tab-border};
  --tab-radius: {d_borderRadius.tab-radius};
  --pf: {d_colors.semantic.primary-focus};
  --pc: {d_colors.semantic.primary-content};
  --sf: {d_colors.semantic.secondary-focus};
  --sc: {d_colors.semantic.secondary-content};
  --af: {d_colors.semantic.accent-focus};
  --ac: {d_colors.semantic.accent-content};
  --nf: {d_colors.base.neutral-focus};
  --nc: {d_colors.base.neutral-content};
  --b2: {d_colors.base.base-200};
  --b3: {d_colors.base.base-300};
  --bc: {d_colors.base.base-content};
}
```


## Contributing

If you would like to contribute to this repository, feel free to create a pull request with your changes.