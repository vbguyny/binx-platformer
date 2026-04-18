# Implementation Tasks

## Milestone 1: Project Skeleton and Core Loop

### Task 1
Description: Create single HTML file scaffold with canvas, HUD containers, start/game-over/win overlays, and responsive layout shell.  
Dependencies: None.  
Acceptance criteria: Opening the HTML shows start screen, canvas area, and adaptive layout placeholders for controls/HUD.  
Estimated complexity: S

### Task 2
Description: Implement fixed timestep game loop and global state machine (boot, playing, paused, level-transition, game-over, win).  
Dependencies: Task 1.  
Acceptance criteria: Loop updates and renders consistently, and state transitions can be triggered manually for testing.  
Estimated complexity: M

### Task 3
Description: Set up virtual-resolution pixel rendering and nearest-neighbor scaling strategy for crisp retro visuals.  
Dependencies: Task 1, Task 2.  
Acceptance criteria: Sprites/tiles appear pixelated without smoothing on desktop and mobile.  
Estimated complexity: S

## Milestone 2: Input and Player Movement

### Task 4
Description: Add keyboard input handler for left, right, and jump with key state tracking.  
Dependencies: Task 2.  
Acceptance criteria: Binx responds to keyboard movement and jump in play state.  
Estimated complexity: S

### Task 5
Description: Add on-screen touch controls (left, right, jump) with hold/tap behavior and mobile-safe hit targets.  
Dependencies: Task 1, Task 2.  
Acceptance criteria: Binx can be fully controlled on touch devices without keyboard.  
Estimated complexity: M

### Task 6
Description: Build Binx entity with gravity, jump, horizontal acceleration/deceleration, and grounded detection.  
Dependencies: Task 2, Task 4.  
Acceptance criteria: Binx movement feels platformer-like and stable across frame rates.  
Estimated complexity: M

## Milestone 3: World, Obstacles, and Levels

### Task 7
Description: Implement tile-based collision and hazard logic including pit detection and respawn/health penalty flow.  
Dependencies: Task 6.  
Acceptance criteria: Solid tiles block movement; pits trigger damage/respawn behavior reliably.  
Estimated complexity: M

### Task 8
Description: Implement moving platform entities with path interpolation and passenger carry behavior.  
Dependencies: Task 7.  
Acceptance criteria: Platforms move predictably and carry Binx while grounded on them.  
Estimated complexity: M

### Task 9
Description: Define level data structure and create at least three levels: basement, kitchen, living room.  
Dependencies: Task 7.  
Acceptance criteria: Each level loads with unique layout/theme and valid spawn/exit points.  
Estimated complexity: M

### Task 10
Description: Add level exit triggers and progression logic across all levels with preserved player health.  
Dependencies: Task 9.  
Acceptance criteria: Reaching exits transitions between levels and final level triggers win state.  
Estimated complexity: S

## Milestone 4: Toby AI and Core Challenge

### Task 11
Description: Implement Toby entity lifecycle and movement controller.  
Dependencies: Task 7, Task 9.  
Acceptance criteria: Toby appears in levels and updates each frame.  
Estimated complexity: S

### Task 12
Description: Add proximity-based detection and chase behavior toward Binx with simple collision-aware movement.  
Dependencies: Task 11.  
Acceptance criteria: Toby starts chasing when Binx is within detection range and follows effectively.  
Estimated complexity: M

### Task 13
Description: Enforce non-defeatable Toby rule and damage/fail consequences on contact.  
Dependencies: Task 12.  
Acceptance criteria: No action can remove Toby; contact always penalizes Binx and can lead to game over.  
Estimated complexity: S

## Milestone 5: Power-Ups and HUD Feedback

### Task 14
Description: Implement power-up entity types: health restore, temporary speed boost, temporary jump boost.  
Dependencies: Task 9, Task 6.  
Acceptance criteria: Collecting each power-up applies the correct effect and removes pickup from map.  
Estimated complexity: M

### Task 15
Description: Implement buff timer system with expiration and value reset to baseline.  
Dependencies: Task 14.  
Acceptance criteria: Temporary boosts expire correctly and do not stack incorrectly beyond defined rules.  
Estimated complexity: S

### Task 16
Description: Build HUD for health, level name, and active buff timers.  
Dependencies: Task 2, Task 15.  
Acceptance criteria: HUD updates in real time and remains readable on desktop/mobile.  
Estimated complexity: S

## Milestone 6: Retro Presentation and Audio

### Task 17
Description: Create simple pixel-art sprite/tile rendering style and room-specific visual palettes for retro SNES feel.  
Dependencies: Task 3, Task 9.  
Acceptance criteria: Basement, kitchen, and living room are visually distinct and consistently retro.  
Estimated complexity: M

### Task 18
Description: Implement WebAudio chiptune-style background music loop with start-on-user-interaction handling.  
Dependencies: Task 2.  
Acceptance criteria: Music plays during gameplay after interaction and can be muted/unmuted.  
Estimated complexity: M

### Task 19
Description: Add simple sound effects for jump, pickup, damage, level complete, and game over.  
Dependencies: Task 18, Task 6, Task 14, Task 13.  
Acceptance criteria: SFX trigger on corresponding events and do not distort or overlap excessively.  
Estimated complexity: S

## Milestone 7: Polish, QA, and Delivery

### Task 20
Description: Implement start, pause, game over, and win screens with restart flow.  
Dependencies: Task 2, Task 10, Task 13.  
Acceptance criteria: Player can start, lose, restart, and win without reloading the page.  
Estimated complexity: S

### Task 21
Description: Tune gameplay parameters (player speed, jump, Toby chase speed, power-up durations, level difficulty).  
Dependencies: Tasks 10 through 16.  
Acceptance criteria: Difficulty curve is fair and all levels are completable with intended challenge.  
Estimated complexity: M

### Task 22
Description: Cross-device validation on desktop and mobile browsers for controls, scaling, and performance targets.  
Dependencies: All prior tasks.  
Acceptance criteria: Game is playable with keyboard and touch, and meets responsiveness/performance requirements.  
Estimated complexity: M

### Task 23
Description: Final single-file integrity check to ensure no external required assets break gameplay offline.  
Dependencies: All prior tasks.  
Acceptance criteria: Opening the HTML file directly in browser loads and runs core gameplay without missing assets.  
Estimated complexity: S
