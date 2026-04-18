# Requirements

## Assumptions
- The game is delivered as one self-contained HTML file with embedded CSS, JavaScript, and audio generation code.
- A single playable character (Binx) and single enemy type (Toby) are required.
- Progression is level-based with at least three house-themed levels: basement, kitchen, and living room.

## Functional User Stories
1. As a player, I want to control Binx with keyboard on desktop, so that I can play on PC naturally.
2. As a player, I want to control Binx with on-screen touch controls, so that I can play on mobile devices.
3. As a player, I want Binx to run, jump, and move through platforms, so that gameplay feels like a classic platformer.
4. As a player, I want pits and moving platforms, so that each level has platforming challenge.
5. As a player, I want Toby to detect and chase Binx when close, so that there is constant stealth-and-escape tension.
6. As a player, I want Toby to be undefeatable, so that avoidance is the core strategy.
7. As a player, I want collectible power-ups for health restore, temporary speed boost, and temporary high jump, so that I can survive and navigate difficult sections.
8. As a player, I want multiple levels set in different house locations, so that the game feels varied.
9. As a player, I want pixelated 16-bit SNES-style visuals, so that the game has retro charm.
10. As a player, I want chiptune-style background music and simple sound effects, so that the audio matches the retro style.
11. As a player, I want clear win/lose conditions, so that I know when I succeed or fail.

## Acceptance Criteria (Gherkin)

### Scenario: Desktop keyboard controls
Given the game is running on a desktop browser  
When the player presses left or right movement keys  
Then Binx moves in the corresponding direction  
And when the player presses jump key  
Then Binx jumps if grounded

### Scenario: Mobile on-screen controls
Given the game is running on a mobile browser  
When the player taps and holds on-screen left or right controls  
Then Binx moves in the corresponding direction  
And when the player taps jump control  
Then Binx jumps if grounded

### Scenario: Toby chase behavior
Given Binx is outside Toby detection radius  
When Binx enters Toby detection radius  
Then Toby changes state to chasing  
And Toby pathing targets Binx position continuously

### Scenario: Toby cannot be defeated
Given Binx collides with Toby or tries to attack  
When an interaction occurs  
Then Toby remains active and unaffected  
And Binx takes damage or triggers fail-state logic

### Scenario: Power-up collection and effect
Given a power-up exists in the level  
When Binx collides with a health power-up  
Then Binx health increases up to max health  
When Binx collides with a speed boost power-up  
Then Binx movement speed increases temporarily  
When Binx collides with a high jump power-up  
Then Binx jump force increases temporarily  
And each temporary effect expires after configured duration

### Scenario: Platforming obstacles
Given a level contains pits and moving platforms  
When Binx falls into a pit  
Then Binx loses health or life and respawns at checkpoint/start  
When Binx lands on moving platforms  
Then Binx is carried by the platform movement while grounded

### Scenario: Multi-level progression
Given Binx reaches the level exit condition  
When exit is triggered  
Then next house location level loads (basement, kitchen, living room sequence)  
And player state transitions correctly between levels

### Scenario: Retro visual and audio style
Given gameplay is active  
When sprites and tiles are rendered  
Then visuals use pixel-art style with crisp nearest-neighbor scaling  
And chiptune-like background music is audible unless muted  
And core actions trigger simple retro sound effects

### Scenario: Win and loss conditions
Given all required levels are completed  
When final level objective is reached without fail-state  
Then the game shows a win screen  
Given Binx health reaches zero  
When no health remains  
Then the game shows a game over screen and restart option

## Non-Functional Requirements
1. Performance: maintain smooth gameplay target of 60 FPS on modern desktop and recent mobile devices, with acceptable fallback above 30 FPS.
2. Compatibility: support latest Chrome, Edge, Safari, and Firefox on desktop and mobile.
3. Input responsiveness: input-to-action latency should feel immediate (target under 100 ms perceived).
4. Accessibility: readable HUD text, high contrast UI elements, and visible touch control hit areas.
5. Reliability: level restart and progression should not corrupt player state.
6. Asset delivery: single HTML file should load and become playable quickly on standard broadband/mobile data.
7. Audio control: allow mute/unmute to respect user environment and mobile autoplay constraints.
