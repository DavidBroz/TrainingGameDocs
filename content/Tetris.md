---
title: Tetris
---
We are making a basic a Tetris game. Blocks fall down, if they complete the row, they disappear. 

## Terminology
These are the terms used in the documentation that need some clarification.
### Block 
Blocks are the shapes that move down the board and that have stopped moving. (example "T block")

### Square 
Square is one possible position on the board. A block can occupy multiple squares it can move between the squares and cannot exist outside of them. The board is made out of squares. 
![[WhatIsBlockAndSquare.png]]
## The board
The board that the blocks falls down on is 10 x 20 squares. Oriented vertically - long side up. 
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
Which block is to be spawn is chosen randomly from all available options. See Block types bellow. 

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
#### Movement down

#### Rotation
