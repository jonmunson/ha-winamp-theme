# Enhanced Mode Setup

The theme works on its own, but the closest Winamp-style result uses `card-mod` as well.

This is what unlocks the extra styling for:

- sidebar chrome
- dialogs and more-info popups
- entity rows
- enhanced card internals
- more detailed media-player styling

## Why it is optional

If you only want the theme colors, card shells, and basic Winamp treatment, you do not need `card-mod`.

If you want the closest clone, you do.

## Setup

1. Install `card-mod` from HACS.
2. Open `Settings -> Dashboards -> Resources`.
3. Find the `card-mod.js` resource HACS added.
4. Copy that resource URL.
5. Add the same URL to `frontend.extra_module_url` in `configuration.yaml`.
6. Restart Home Assistant.
7. Keep the original HACS dashboard resource in place.

Example configuration:

```yaml
frontend:
  themes: !include_dir_merge_named themes
  extra_module_url:
    - /hacsfiles/lovelace-card-mod/card-mod.js?hacstag=YOUR_HACS_TAG
```

## Important Notes

- The `hacstag` value is specific to your Home Assistant instance.
- If you change `extra_module_url`, restart Home Assistant.
- This step is required because some parts of Home Assistant, including the sidebar and dialogs, are outside the scope of normal dashboard-only styling.
