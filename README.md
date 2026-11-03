# PdfCraft Thai — release channel

Reviewed builds of PdfCraft with Thai text editing (Express quotations) and Thai + English OCR,
used inside our company. The app's built-in updater reads **this** repository's latest release
instead of upstream, so a new upstream version reaches our PCs only after we have rebased our
changes, tested them and published a release here.

- Upstream: https://github.com/storytold/pdfcraft (MIT OR Apache-2.0). This build keeps the
  upstream licences and notices inside the zip (`LICENSE-*`, `NOTICE`, `licenses/`, `OCR-NOTICE.txt`).
- Every release carries `pdfcraft-<version>-windows-x64-portable.zip`, `SHA256SUMS.txt` and
  `SHA256SUMS.txt.sig` (Ed25519). The app installs an update only if that signature verifies
  with the public key built into it: `3aJjtubFcKcmXbD66/513XF5+enoTqFSF96XLkUqYyk=`.
- Binaries are not code-signed.
- Fonts are not shipped here; no customer documents are ever attached.

## Versions

`0.<upstream minor>.<upstream patch × 100 + our build>` — e.g. upstream 0.18.0 → 0.18.1, 0.18.2 …;
upstream 0.18.1 → 0.18.101 … Always higher than the build it replaces.

## Release checklist (maintainers)

1. Rebase the patches onto the new upstream tag, build, run the test matrix and look at the renders.
2. Bump the version, package, compute SHA-256.
3. Publish: `gh release create v<ver> <zip> SHA256SUMS.txt third-party-sources/jbigkit/* third-party-sources/libiconv/*` + `SHA256SUMS.txt.sig` — only after review.

## Third-party sources

GPL components in the OCR bundle have their complete source in `third-party-sources/` and attached to
each release (JBIG-KIT 2.1 under GPL-2.0+, GNU libiconv 1.17 under LGPL-2.1+; see the README in each folder).
