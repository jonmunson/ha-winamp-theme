# Full Fidelity Setup

The theme file works by itself, but the closer Winamp clone depends on `card-mod` theme variables such as `card-mod-root`, `card-mod-card`, `card-mod-row`, `card-mod-sidebar`, `card-mod-more-info`, and `card-mod-dialog`.

## Why card-mod is needed

Home Assistant theme variables can recolor many components, but they cannot fully restyle global chrome such as the header, sidebar, dialog shell, or entity-row internals. `card-mod` can, and its official theme docs support these theme variables directly.

## Install steps

1. Install `card-mod` from HACS.
2. Open `Settings -> Dashboards -> Resources`.
3. Find the HACS-added `card-mod.js` resource URL.
4. Add that URL to `frontend.extra_module_url` in `configuration.yaml`.
5. Restart Home Assistant.
6. Keep the HACS dashboard resource entry in place.

Example:

```yaml
frontend:
  themes: !include_dir_merge_named themes
  extra_module_url:
    - /hacsfiles/lovelace-card-mod/card-mod.js?hacstag=YOUR_HACS_TAG
```

## Notes

- The `hacstag` value will be specific to your Home Assistant instance.
- If you change `extra_module_url`, restart Home Assistant.
- Styling the sidebar outside Lovelace dashboards requires `card-mod` to be loaded as a frontend module, not only as a dashboard resource.
