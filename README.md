# Ringlight Burst

A small, dependency-free visual experiment that simulates a glowing ring light with layered CSS shapes, blur, color shifts, and slow rotation.

Everything runs in the browser from a single file: [`index.html`](./index.html).

## Preview

The page renders three overlapping light layers on a black background:

- an expansive warm outer glow;
- a bright white central glow;
- a smaller orange inner glow.

The layers rotate and pulse at different speeds to create a soft, organic burst effect.

## Run locally

No build step or dependency installation is required. Open `index.html` directly in a browser, or serve the folder with any local HTTP server:

```bash
python -m http.server 8000
```

Then visit <http://localhost:8000>.

## How it works

The effect is built with three `.burst` elements inside a centered `.stack` container. Each layer uses CSS custom properties for its size, color, and blur amount:

```css
.main {
  --s: 60vmin;
  --c: #ffffff;
  --b: 88px;
}
```

The `spinPulse` animation combines rotation and scaling, while `warmCool` gently shifts the hue over time. The `::before` and `::after` pseudo-elements rotate copies of each layer to form the burst shape.

## Customize it

Edit the variables in `index.html` to change the appearance:

- `--s`: layer size;
- `--c`: base color;
- `--b`: blur radius;
- animation durations: movement and color-transition speed.

The page also respects `prefers-reduced-motion` and disables the animations when the user has requested less motion in their operating-system settings.

## Project structure

```text
ringlight/
|-- index.html   # Markup, styles, and animations
`-- README.md    # Project documentation
```

## License

No license has been specified yet.
