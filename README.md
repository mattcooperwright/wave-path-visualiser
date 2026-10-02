# Wave Path Visualiser

An interactive animation tool for creating flowing, gradient-coloured line animations with draggable control points and high-resolution export.

## Features

- **Draggable control points** — click and drag anchor points to shape the line path
- **Smooth spline interpolation** — creates flowing, organic curves
- **Colour gradients** — assign colours to anchor points with smooth interpolation between them
- **Animated wave motion** — the line oscillates with adjustable amplitude, speed, and frequency
- **Grain texture** — procedural noise for a print-like finish
- **Customizable appearance** — control tube width, smoothness, grain, and background colour
- **High-resolution PNG export** — export at up to 6x screen resolution
- **Keyboard interactions** — double-click to add points, alt-click to delete points

## How to Use

1. **Select a point** — click any anchor point (the coloured circles)
2. **Recolour** — use the colour picker or preset swatches in the panel
3. **Add a point** — double-click anywhere on the line
4. **Delete a point** — alt-click any anchor point
5. **Move points** — drag any anchor point around the canvas
6. **Adjust animation** — use the controls to tweak wave properties
7. **Hide controls** — click "Hide controls" to see the animation fullscreen
8. **Export** — adjust PNG scale and click "Save hi-res PNG"

## Transparent Video Export (`/video`)

`video.html` is a separate version of the tool for motion work. It draws the wave on a fixed-size artboard (HD, 4K, square, 4:5 or vertical) with no background, and exports:

- **ProRes 4444 `.mov` with alpha**, for After Effects, Premiere, Final Cut, DaVinci Resolve and Keynote. Encoding runs in the browser with [ffmpeg.wasm](https://github.com/ffmpegwasm/ffmpeg.wasm). The first export downloads a 31 MB encoder from jsDelivr, which the browser then caches.
- **PNG sequence `.zip` with alpha**, a lossless fallback that imports into any editor as an image sequence.
- **Green screen `.mp4`**, for apps that ignore transparency, such as iMovie. Put it above your footage and choose the Green/Blue Screen overlay to key out the green.

Frames are rendered one by one at the chosen frame rate rather than screen-recorded, so the output is smooth on any machine. "Seamless loop" sets the length to a whole number of motion cycles, so the clip loops without a jump.

MP4 (H.264) cannot store transparency, which is why the export uses ProRes. Long 4K exports can run out of browser memory; use a shorter length or the PNG sequence if that happens.

## Running Locally

```bash
npm run dev
```

Then open http://localhost:8000 in your browser.

## Deploying to Vercel

1. **Initialize a git repository** (if not already done):
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   ```

2. **Push to GitHub**:
   - Create a new repository on [GitHub](https://github.com/new)
   - Push your local code: `git remote add origin <your-repo-url>` and `git push -u origin main`

3. **Connect to Vercel**:
   - Go to [vercel.com](https://vercel.com)
   - Sign in or create an account
   - Click "New Project"
   - Select your GitHub repository
   - Click "Deploy"

That's it! Your tool will be live at a Vercel URL. Every time you push to GitHub, it will automatically deploy.

## Customizing

Edit `index.html` to modify:
- Default colours in the `palette` array
- Default point positions and colours in `defaultPoints()`
- Control panel parameters (min/max values)
- Animation logic in the animation section

## License

MIT
