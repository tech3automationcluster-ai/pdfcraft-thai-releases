# PdfCraft Thai — release channel

Reviewed builds of PdfCraft with Thai text editing (Express quotations) and Thai + English OCR,
used inside our company. The app's built-in updater reads **this** repository's latest release
instead of upstream, so a new upstream version reaches our PCs only after we have rebased our
changes, tested them and published a release here.

- Upstream: https://github.com/storytold/pdfcraft (MIT OR Apache-2.0). This build keeps the
  upstream licences and notices inside the zip (`LICENSE-*`, `NOTICE`, `licenses/`, `OCR-NOTICE.txt`).
- Every release carries `pdfcraft-<version>-windows-x64-portable.zip` and `SHA256SUMS.txt`.
- Binaries are not code-signed.
- Fonts are not shipped here; no customer documents are ever attached.

## Versions

`0.<upstream minor>.<upstream patch × 100 + our build>` — e.g. upstream 0.18.0 → 0.18.1, 0.18.2 …;
upstream 0.18.1 → 0.18.101 … Always higher than the build it replaces.

## Release checklist (maintainers)

1. Rebase the patches onto the new upstream tag, build, run the test matrix and look at the renders.
2. Bump the version, package, compute SHA-256.
3. Publish: `gh release create v<ver> <zip> SHA256SUMS.txt` — only after review.
