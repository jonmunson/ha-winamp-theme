# Winamp Classic for Home Assistant

Home Assistant theme tuned to the classic default Winamp 2.x skin: silver gunmetal chrome, blue selection states, amber controls, and green LCD-style display accents.

![Winamp Classic preview](docs/preview.svg)

## What this is

This repository is structured as a HACS theme repo, so once it is pushed to GitHub it can be added to any Home Assistant instance through HACS as a custom repository.

The theme is tuned around the default classic skin cues:

- silver and gunmetal chrome
- blue selection and focus states
- amber transport-style controls
- green LCD display accents
- square edges and hard beveled cards

## Installation

Add the following to your `configuration.yaml` if you do not already load themes:

```yaml
frontend:
  themes: !include_dir_merge_named themes
```

Restart Home Assistant after changing `configuration.yaml`.

### HACS

1. Push this repository to GitHub.
2. In Home Assistant, open HACS.
3. Open the menu in the top right and choose `Custom repositories`.
4. Add your GitHub repository URL and select the `Theme` category.
5. Install `Winamp Classic`.
6. Run the `frontend.reload_themes` action, or restart Home Assistant.
7. Select `Winamp Classic` in your user profile.

### Manual

1. Copy `themes/winamp_classic.yaml` into your Home Assistant `themes/` directory.
2. Run the `frontend.reload_themes` action, or restart Home Assistant.
3. Select `Winamp Classic` in your user profile.

## Repo layout

- `themes/winamp_classic.yaml`: theme definition HACS installs
- `hacs.json`: HACS manifest for a single theme file
- `.github/workflows/validate.yaml`: HACS validation workflow

## Notes

Home Assistant themes can control colors, spacing, shadows, and many component surfaces, but they cannot fully recreate the bitmap skinning system Winamp used. This theme is biased toward the default 2.x palette and chrome treatment without requiring extra custom cards.

If you want a more extreme recreation later, the next step would be pairing this theme with dashboard-level styling such as `card-mod`, image assets, and a custom view layout that mimics the Winamp player frame.
