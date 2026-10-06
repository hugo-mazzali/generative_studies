# Emergence Studies

Three rule systems that grow shapes on their own, react to music, and turn a whole song into a single image.

![Emergence Studies: switching between SmoothLife, Particles and Reaction, with and without music](emergence-studies.gif)

Built by Hugo Mazzali as a generative and interactive art project. It runs entirely in the browser (WebGL2); there's nothing to install.

**Live version:** open `index.html` in a recent desktop browser, or visit the GitHub Pages link for this repository.

## The three systems

| System | What it is | What to look for |
|---|---|---|
| **SmoothLife** | Conway's Game of Life with smooth values instead of on/off cells. Each pixel compares a small disk around it with a wider ring. | Gliders, blobs with holes, amoebas that bud off new creatures |
| **Reaction** | Gray-Scott reaction-diffusion: two simulated chemicals spread and react. | Cells that divide (Mitosis), coral, worms, mazes |
| **Particles** | Particle life: each color of particle is attracted to or pushed away from the others by random rules. Drawn as metaballs, so clusters melt together. | Cells, chains, groups that chase each other |

All three share one renderer: a heat-map palette, film grain, glow and rim light on a warm near-black background, inside a frame that keeps everything on screen.

## Projector output

**Open output window** opens just the animation (no controls) in a second window. Drag it onto the projector and double-click it for full screen (Esc or double-click again to leave). The controls window keeps a live preview in the same shape, where you can still draw and drag the frame, and keyboard shortcuts work in either window. Keep the controls window open (not minimized) so the animation keeps running. With one screen, **Full screen here** hides the controls and fills the screen (Esc brings them back).

## Frames

The picture can hold up to 4 frames, each running its own system with its own preset, palette, position and shape. **+ Add frame** adds one (the next system and palette), **Remove frame** removes the selected one. Click inside a frame (or its chip in the panel) to select it; the system tabs, presets, rules, brush, frame shape and palette in the panel all change the selected frame. Rules sliders are shared by frames running the same system.

Drag any frame's edge to move it, or a corner to resize it (handy for lining frames up with a projection surface). **Fluid** hides the selected frame's line and replaces its hard wall with a soft, invisible boundary that wobbles and swells with the music: shapes fade out gently as they drift past it and particles are pulled back in, so the system's own shapes form the edge (the line shows faintly only while you hover over it to drag). **Reset frame** fits the selected frame to the screen again.

## Music

- **Load a song** (MP3, WAV, M4A) or use the built-in **Demo beat**. Audio is analyzed live in the page; nothing is uploaded anywhere.
- **Song position**: drag the slider under the track name to jump to any part of a loaded song.
- **Beats push the shapes around**: each beat sends a shockwave from a random point that shoves and spins nearby shapes. **Beat sensitivity** and **Beat push** tune how much the music moves things.
- **The song steers the rules**: brightness (treble vs bass) moves the feed rate and blends the colors, and loudness changes pattern scale and hue. Steering is gentle in soft passages and strong in full ones.

## Song portrait

Load a song and choose **Make song portrait**. The page:

1. Analyzes the whole song (loudness, brightness, beat density, pauses) and cuts it into at least 5 parts where the music changes most.
2. Gives each part the system that fits its sound (quiet and sparse → SmoothLife, steady → Reaction, loud or beat-heavy → Particles), so all three systems appear.
3. Plays the song once on one large canvas that grows outward from the center. Each part grows its system in the space the growth front opens up, and when the song moves on, that part settles: it keeps swaying very slightly with the music while the next part grows around it. Nothing is cycled away: the canvas only gets added to.
4. Saves the finished canvas as one landscape image (3600 px wide), with a timeline of the parts underneath.

## Controls

| Key | Action |
|---|---|
| `1` `2` `3` | Switch system |
| `R` | Reseed |
| `C` | Clear |
| `Space` | Pause |
| `M` | Music on/off |
| `F` | Fluid / straight frame |
| `H` | Hide the control panel |
| Drag | Seed / push (hold `Shift` to erase / pull); drag the frame edge to move it, a corner to resize |


## Credits

- SmoothLife: Stephan Rafler, "Generalization of Conway's Game of Life to a continuous domain" (2011)
- Gray-Scott reaction-diffusion: P. Gray and S. K. Scott; parameter presets after Karl Sims' and Robert Munafo's explorations
- Particle life: after Jeffrey Ventrella's "Clusters" and Tom Mohr's particle life
- Fonts: Bricolage Grotesque and IBM Plex Mono, via Google Fonts
