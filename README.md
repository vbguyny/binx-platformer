# Binx Platformer

Single-file retro platformer built to match the project requirements.

## Run

1. Open `index.html` in a modern browser (Chrome, Edge, Firefox, or Safari).
2. Click **Start Game**.
3. Audio initializes after your first interaction due to browser autoplay rules.

## Controls

- Desktop:
	- Move: `A` / `D` or `Left` / `Right`
	- Jump: `W`, `Up`, or `Space`
	- Pause: `P`
	- Mute toggle: `M` or HUD mute button
- Mobile:
	- On-screen `Left`, `Right`, and `Jump` buttons

## Gameplay

- Complete three levels in order: basement, kitchen, living room.
- Avoid Toby. He chases nearby and cannot be defeated.
- Collect power-ups:
	- Health restore
	- Temporary speed boost
	- Temporary jump boost
- Reach the exit in each level to progress.
- Lose when health reaches zero.
- Win after clearing the final level.

## Notes

- Rendering uses a virtual low resolution with nearest-neighbor scaling for pixel style.
- Music and SFX are generated with the WebAudio API; no external assets are required.
