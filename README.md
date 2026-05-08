# Wand & Widgets — Marketing Assets

Public CDN-friendly assets for our Foundry VTT modules: screenshots, banners, demo stills, and brand pieces. Hosted here so Foundry package descriptions and other public-facing surfaces can reference stable URLs without depending on Discord, Patreon, or other CDNs that expire.

## Folder structure

- `narrator-jukebox/` — assets for [Narrator's Jukebox](https://foundryvtt.com/packages/narrator-jukebox)
- `exalted-scenes/` — assets for [Exalted Scenes](https://foundryvtt.com/packages/exalted-scenes)
- `shared/` — brand pieces shared across modules (logos, banners, etc.)

Folders are created as content is added.

## Usage — jsDelivr CDN

GitHub raw URLs work, but [jsDelivr](https://www.jsdelivr.com/) is faster, has global CDN caching, and serves proper `Content-Type` headers — strongly recommended for embeds in package descriptions.

**URL pattern:**

```
https://cdn.jsdelivr.net/gh/wand-and-widgets/marketing-assets@main/<module>/<file>
```

**Example:**

```
https://cdn.jsdelivr.net/gh/wand-and-widgets/marketing-assets@main/exalted-scenes/screenshot-01-gm-panel.png
```

**Pinning to a tag** (recommended for shipped descriptions, so future asset edits don't change live screenshots):

```
https://cdn.jsdelivr.net/gh/wand-and-widgets/marketing-assets@v1/exalted-scenes/screenshot-01-gm-panel.png
```

After updating any module's assets, tag a new version (`git tag v2 && git push --tags`) and update the embed URLs.

## Image guidelines

- **Screenshots:** 1280–1920 px wide, PNG. Compress with [TinyPNG](https://tinypng.com/) or `pngquant` to keep file sizes reasonable.
- **Banners:** 16:9 or 21:9 ratios.
- **Demo videos:** prefer GIFs ≤ 5MB; longer clips go on YouTube and link from the package description.
- **File names:** lowercase, hyphenated, descriptive: `screenshot-01-gm-panel.png`, `banner-cinematic.png`, `demo-emotion-picker.gif`.
- **No private data:** make sure no real session content, real player names, or unintentional sensitive info is captured.

## Embedding in Foundry package descriptions

Foundry's rich-text editor accepts HTML via the `<>` button. Use `style="max-width: 100%; height: auto;"` so images scale within the description without anamorphic distortion.

**Single screenshot with caption:**

```html
<p>
  <img src="https://cdn.jsdelivr.net/gh/wand-and-widgets/marketing-assets@main/exalted-scenes/screenshot-01-gm-panel.png"
       alt="GM Panel — scene library with cast preview"
       style="max-width: 100%; height: auto;">
</p>
<p><em>The GM Panel — your scene and character library, theme-tinted, ready to broadcast.</em></p>
```

**Side-by-side screenshots** (two-column layout):

```html
<table style="border: none; width: 100%;">
  <tr>
    <td style="width: 50%; padding-right: 4px; border: none;">
      <img src="https://cdn.jsdelivr.net/gh/wand-and-widgets/marketing-assets@main/exalted-scenes/screenshot-token.png"
           alt="Token mode" style="max-width: 100%; height: auto;">
      <p style="text-align: center;"><em>Token Mode</em></p>
    </td>
    <td style="width: 50%; padding-left: 4px; border: none;">
      <img src="https://cdn.jsdelivr.net/gh/wand-and-widgets/marketing-assets@main/exalted-scenes/screenshot-hero.png"
           alt="Hero mode" style="max-width: 100%; height: auto;">
      <p style="text-align: center;"><em>Hero Mode</em></p>
    </td>
  </tr>
</table>
```

## License

All assets in this repository are © Wand & Widgets and are distributed for the purpose of representing the Wand & Widgets modules on the Foundry VTT package directory and related promotional surfaces. Do not redistribute without permission.

---

Crafted with love, from one storyteller to another. ❤️

— Wand & Widgets
