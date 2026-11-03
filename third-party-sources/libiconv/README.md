# GNU libiconv source (LGPL-2.1-or-later)

The Thai OCR bundle ships `ocr/tesseract/libiconv-2.dll` (GNU libiconv 1.17, as reported by the
DLL's `_libiconv_version`, built by MSYS2 and shipped in the UB-Mannheim Tesseract 5.4.0 build).
It is a separate, replaceable DLL. Its source:

| File | SHA-256 | Origin |
|---|---|---|
| libiconv-1.17.tar.gz | 8f74213b56238c85a50a5329f77e06198771e70dd9a739779f4c02f65d971313 | https://ftp.gnu.org/pub/gnu/libiconv/ |
| libiconv-1.17.tar.gz.sig | 06d1357471c445eb6c0b6a568b79dac3f46003b9efcb5fee2208aad33fc54cab | GNU signature |

The MSYS2 build recipe for 1.17 is no longer on repo.msys2.org; the recipe history is at
https://github.com/msys2/MINGW-packages/tree/master/mingw-w64-libiconv . We did not modify libiconv.
