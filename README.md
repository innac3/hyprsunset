## hyprsunset
An application to enable a blue-light filter on Hyprland

> !IMPORTANT!
> This app requires hyprland>=0.45.0

## Docs / Configuration
[See the wiki](https://wiki.hypr.land/Hypr-Ecosystem/hyprsunset/)

## Support

This utility relies on support for `hyprland-ctm-control-v1` by the compositor, so
it's most likely hyprland-exclusive.

## Saturation / grayscale

Use `hyprsunset --saturation 0` (or `-s 0`) for grayscale, `-s 50` for
partial desaturation, and `-s 100` for full color (the default). Values may
be fractional and must be between 0 and 100. Temperature and gamma still
apply; grayscale can therefore retain the selected warm or cool tint.
`--identity` bypasses temperature and saturation, preserving its existing
gamma behavior.

Scheduled `profile` blocks accept `saturation = 50` using the same 0–100
scale. Omitting it preserves full color. The CLI overrides the initial
profile; subsequent scheduled switches use the new profile's saturation.

Runtime commands: `hyprctl hyprsunset saturation` queries the percentage,
`hyprctl hyprsunset saturation 50` sets it, and signed values such as
`hyprctl hyprsunset saturation -10` adjust it (clamped to 0–100).
`hyprctl hyprsunset reset saturation` restores the current profile's value.
