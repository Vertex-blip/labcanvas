# LabCanvas

<img src="./logo.svg" width="48" height="48" alt="LabCanvas logo">

An interactive physics lab with three browser-based simulations: pendulum, projectile motion, and a spring oscillator. The hero instrument is a live view of the selected model. Change variables, pause or restart the system, read live measurements, and download numeric data as CSV.

## Run

Open `index.html` in a modern browser, or publish the repository root with GitHub Pages. There is no build step, account, API key, or backend.

## Experiments

| Experiment | Controls | Model |
| --- | --- | --- |
| Pendulum | Length, starting angle, gravity, damping | Nonlinear angular acceleration: `θ″ = -(g/L)sin(θ) - bθ′` |
| Projectile | Speed, launch angle, gravity | Ideal ballistic trajectory with no drag |
| Spring | Mass, stiffness, displacement, damping | Hooke's law: `x″ = -(k/m)x - bx′` |

The models are intentionally simplified. The displayed **ideal period** formulas ignore damping. The pendulum period estimate also assumes a small angle. The projectile range assumes a level launch and landing. Numerical integration uses time steps of at most 0.01 seconds for the pendulum and spring.

**Download data** exports the current run's samples at roughly 0.1 second intervals. Changing a control starts a fresh run. `Space` toggles play and pause when focus is outside an interactive control.

## Project structure

- `index.html` — lab and field notes
- `style.css` — responsive design
- `app.js` — physics models, canvas rendering, controls, and CSV export

No runtime dependencies or third-party requests. Typefaces are bundled under `fonts/` with their OFL licenses. All computations happen in the browser.

## License

MIT. See [LICENSE](LICENSE).
