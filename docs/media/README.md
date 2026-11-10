# Media

Brand assets for the Maturity Model for Microsoft 365. Use them on the site, in decks and on social media.

| Folder | What | Example |
| --- | --- | --- |
| `banners/` | 1200 × 300 banners | `competency-security-300.svg` |
| `icons/` | One icon per competency, plus one for scenarios and one for tools | `competency-search.svg` |
| `logo/` | The logo | `mm4m365-logo-square.svg` |
| `animations/` | Animated SVGs | `loader-equalizer.svg` |

`logo.svg`, `M365MM.png`, `pnp-mm4m365-blue.svg` and `favicon.ico` stay in this folder because the site template and many pages link to them.

## Naming

All names are lowercase, words separated by hyphens, `&` written as `and`. The competency part matches the competency name, for example `governance-risk-and-compliance`.

| Banner | Name |
| --- | --- |
| Competency at a level, all levels shown, active one wider | `competency-<competency>-<level>.svg` |
| Same, only the active level | `competency-<competency>-<level>-single.svg` |
| Same, all levels equal width | `competency-<competency>-<level>-equal.svg` |
| How to elevate, from one level to the next | `elevate-<competency>-<from>-<to>.svg` (plus `-single`, `-equal`) |
| Practical scenario | `scenario-<title>.svg` |
| Tools and samples | `tool-<title>.svg` |
| The model | `model.svg` |

## Colors

One color per level, taken from the logo in its column order. Only purple carries white text. The other four carry dark text (`#24264f`), so every label passes WCAG AA contrast.

| Level | Color | Text on it |
| --- | --- | --- |
| 100 Initial | `#6A6DAD` | white |
| 200 Managed | `#03A4EF` | dark |
| 300 Defined | `#F15021` | dark |
| 400 Predictable | `#81BB04` | dark |
| 500 Optimizing | `#FEBB0A` | dark |

Competencies have no color of their own. Color always means level.

## How the files are made

The banners come from the [banner builder](../tools-samples/files/banner-builder.html). Text is converted to outlines (Roboto), so a banner looks the same in a browser, in PowerPoint and on a machine without the font. To make a banner that is not here, build it in the banner builder and download it as SVG; the builder names the file by the table above. A downloaded banner uses the Roboto font as live text rather than outlines, so it looks right in a browser and where Roboto is installed.

Icons: [Fluent UI System Icons](https://github.com/microsoft/fluentui-system-icons), MIT License, Copyright (c) Microsoft Corporation. Font: Roboto, SIL Open Font License 1.1.
