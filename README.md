# Bomberman World — Kaffe Rast

**Student:** Rasmus Stenberg

> Replace the prompts below and remove these instructions. Keep answers brief. Your implementation explanations and reflection belong in the presentation; you do not need to write them out here. Complete the final section only if seeking Pass with Distinction (VG).

## How to play

- **Controls:**
  - Move with WASD
  - Place a bomb with SPACE
- **Objective and rules:**
  - After all enemies are defeated on the stage a blue portal will spawn in the top left corner and take you to the next        stage
- **Configurations / demo setup:**
  - Pressing P will give you a power up without needing to pick up one 

## Features and validation

(delete this pre-amble before submitting the assignment) Complete the five required features and three extensions of your choice. For each row, document **at least one useful check: what you tested, what you observed, and how the result compares with the expected behaviour**. One or two sentences per feature are enough. Choose a check that could reveal a mistake, such as a boundary case or interaction.

Use the practical checks in the assignment to validate the acceptance conditions during development; this table is a small sample of that work. Manual play in a small, repeatable setup is sufficient. You can also use a debugger, temporary logging, or small scenarios set up in code. Screenshots, recordings, automated tests etc are welcome, but not required. Be ready to explain the relevant rules in your code.

| Feature | Check, observed result, and expected behaviour |
| --- | --- |
| 1. Player damage and death | When I stood in my own bombs explosion the player took 1 damage as expected  |
| 2. Round states and objective | There is a start scene, game state, and a game over screen, moving between states is smooth and being in a state never influences another state. Killing all enemies also complets a stage and spawn the portal to the next stage. The objective is not dying and to keep going as far as possible like tetris |
| 3. Safe restart | After getting a game over and reseting back to the start screen and starting the game again all values were reset or returned to its original value additonaly gameplay only happens in the gameplay state (making rooms, spawning enemies, etc) so there is no gameplay happening in the background when in start screen|
| 4. Solid bombs with owner escape | When a bomb was placed it was solid for enemies and the player after the player moved away from the bomb so everything is working as intended  |
| 5. Blast-range pickup | Enemies drop a pickup when killed (30% chance) and it does not get removed when in an explosion and stays on the stage until collected and when picked up increases explosion range by 1 (max of 3) and also gives the player one more bomb at a time and it works as it should, reseting the game also removes any power up from the previous round |
| 6. Multiple bombs per owner | After getting a power up and only after getting a power up the player can place another bomb while there already is another bomb present on the stage. The new bomb doesnt replace another bomb but places anotherone one the board with its own fuse, and it does what it meant to do with the player being able to place another bomb equal to the amount of powerups they have collcted on that run  |
| 7. Chain reactions | When another bomb hits a bomb the bomb that was hit ignores it fuse for another a short delay instead (0,4 sec which is 0,5 sec longer than the visual explosion for a bomb) and it also does what is supposed to do a bomb makes another bomb explode, one bomb can hit multiple bombs however causing multiple explosions at once which makes sense since they got hit at the same time.  |
| 10. Exit or progression gate| After defeating all enemies on a stage the portal appears in the place as the player spawns in when entering a room, the portal is however the edge of a tile so it covers the halfs of two tiles. It probablt has to do with where positions are calculated (top left or bottom right corner etc) But touching the portal takes the player to new stage that has new enemies, crate positions, and is also bigger whilst the player keeping all power up and previous health  |

**Known issues:** 
- Since blast detection is instant and before any visuals you dont even see the bomb that kills you you just "randomly" and instatly go to the game over screen
- Bombs placed on the same tile as a crate does not render but still explodes (with explosion visual) and damages the player
- The enemies dont deal any damage to the player (not an issue i didnt implement that)  

## Sources and assistance

This project builds on the shared Kotte foundations.
The presentations from previous weeks were useful to look at and understand the code that came with the assignemnt. Asking a classmate to get some insight was good. Github copilot was also helpful for explanations and as assitance when totally lost. 

<!-- Submission: commit and push this README with your source to GitHub or the internal Gitea server. Submit the final commit link and a runnable Release ZIP from that version in Studium. Ensure the teacher can access the repository throughout assessment. -->
