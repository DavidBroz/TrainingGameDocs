---
title: Tetris
---
We are making a basic Tetris game. Blocks fall down, if they complete the row, they disappear. 

## Terminology
These are the terms used in the documentation that need some clarification.
### Block 
Blocks are the shapes that move down the board and that have stopped moving. (example "T block")

### Square 
Square is one position on the board. A block can occupy multiple squares it can move between the squares and cannot exist outside of them. The board is made out of squares. 

![[WhatIsBlockAndSquare.png]]
## The board
The board that the blocks falls down on is 10 x 20 squares. Oriented vertically. 
![[tetris_board.png]]

## Block movement
Blocks move on their own in one direction at set speed and can be also controlled by the player. At any given time **only one block can move** at a time. 

### Automatic movement
Every block starts the the middle top of the board and moves at set speed to the bottom of the board. Default setting should be **1 square/second** but this speed should be **adjustable mid play**.   
![[blocks_falling.png]]

#### Stopping of movement
When a block reaches the bottom of the board and **tries to move** outside of the board or into a space occupied by another block, then it stops moving. Only movement down can stop a block.
![[block_movement_stops.png]]![[moving_stop_on_block.png]]

#### Block spawn
When there is no moving block to be moved when it is time to move it, a new moving block will be spawn at the **top middle** of the board. If the block cannot fit perfectly into the middle position, it will be spawn on the right side of the middle position.![[block spawn.png]]
Which block is to be spawn is chosen randomly from all available options (see [[Tetris#Block Types|Block types]]). 

### Player controlled movement
Player has control over 3 aspects for the block. Movement side to side, movement down, and rotation of the block.

#### Movement side to side
Player can move the block one square to left or right with keyboard inputs. Upon pressing of a button to move, the game checks 2 conditions about the squares the block wants to move into:
1. Are any of them occupied by another block?
2. Are any of them outside of the board?
If either is true, the movement input is ignored. If neither are true, the block is immediately moved one square in the direction of the input. 
##### Keyboard inputs
- Move left: A or Left Arrow
- Move right: D or Right Arrow

![[ignored_input.png]]
![[processed_movement.png]]
#### Movement down
Player can also move the block down with keyboard input. They can either move it immediately one square down or "slam it" which means to move it down until it stops (there is no more squares to move it to).
##### Keyboard inputs
- Move down: S or Down Arrow
- Slam block: Space  
![[player_movement_down.png]]
![[player_slamming_block_example.png]]
#### Rotation
Player can rotate the moving block 90° left or right. Each block rotates around a specified point of the block (see [[Tetris#Block Types|Block types]])
##### Keyboard inputs
- Rotate left: Q
- Rotate right: E

#### Kickback
Kickback is a mechanic the game uses for when a block rotates into a square that is outside of the board or occupied by another block. When this occasion happens the block should be **kicked back** to a square, where there is no collision anymore. The direction of the movement should be with these priorities:
1. Move the block the smallest number of one square moves possible 
2. Move block to one square left
3. Move block to one square right
4. Move the block one square up

![[rotation_kickback.png]]
### Block Types
These are the block types that inside the game. Every block is consists of 4 connected squares. The following symbol shows around which point does the block rotate:
![[point_of_rotation.png]]
#### I block
![[I_block_rotation.png]]
#### L block
![[L_block_rotations.png]]
#### Reverse L block
![[reverse_L_block_rotations.png]]
#### T block
![[T_block_rotations.png]]
#### Z block
![[Z_block_rotations.png]]
#### S block
![[S_block_rotation.png]]

### Completing a row

When the player manages to complete a full row of the block on the board, the row disappears and all blocks above the row move one spaces down. If multiple rows are completed at the same time, all the rows disappear at the same time and the blocks one square down for each completed row bellow them.

![[row_completion.png]]

## Game ending
Player loses and the game is over when a block stops moving and part of it is not on the board.
 
![[game_over_examples.png]]