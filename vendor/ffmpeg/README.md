# @ffmpeg/ffmpeg 0.12.15 (ESM build)

Unmodified copy of the `dist/esm` JavaScript from [ffmpeg.wasm](https://github.com/ffmpegwasm/ffmpeg.wasm) (MIT licence).

It is served from this site rather than a CDN because the library starts a Web Worker from its own URL, and browsers only allow same-origin worker scripts. The large encoder core (`@ffmpeg/core`) is still loaded from jsDelivr by `video.html` when an export is first run.
