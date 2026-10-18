# Cognio-Templates-Public

Public repository for released Cognio templates: sites, spaces, themes and
module configurations.

## Template library website

`index.html` is a self-contained, dependency-free page that lists every
released template and lets you filter by template type and author. It reads
`index.json` (regenerated automatically by the release pipeline in the private
`Cognio-Templates` repo) and links to each template's download. Its layout
mirrors the Cognio Driver Library in `cognio-drivers-public`.

Once GitHub Pages is enabled (Settings → Pages → Deploy from a branch →
`main` / root), the library is published at:

**https://symetrix-audio.github.io/Cognio-Templates-Public/**

## Contents

- `index.html` — the template library page (hand-written, no build step). Each
  card shows the template's name, author, type and version, its description,
  and — when the template ships a preview image — a clickable thumbnail that
  opens full size in a lightbox.
- `index.json` — machine-readable catalog of released templates, regenerated on
  each release. Each entry carries `type` (`site`, `space`, `theme` or
  `module-configuration`), `name`, `version`, `description`, `author`, `path`
  and `downloadUrl`, plus `imagePath` / `imageUrl` only when a preview image was
  shipped — so an imageless template still renders cleanly.
- `sites/`, `spaces/`, `themes/`, `module-configurations/` — one folder per
  released template, `<type-dir>/<Folder>/`, holding the template file, its
  `<Name>-info.json` metadata and (when provided) its `<Name>-image.png`
  preview. All created and maintained automatically by the release pipeline;
  do not edit by hand — every release rebuilds these folders from scratch.
- `.nojekyll` — tells GitHub Pages to serve the files as-is without a Jekyll
  build.
