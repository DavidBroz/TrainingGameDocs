---
title: Tetris
---
We are making a basic a Tetris game. Blocks fall down, if they complete the row, they disappear.

## The board
The board that the blocks falls down on is 10 x 20 blocks. Oriented vertically - long side up. 
![[tetris_board.png]]

## Block movement
Block move on their own in one direction at set speed and can be also controled by the player.

### Automatic movement
Every block starts the the middle top of the board and moves at set speed to the bottom of the board. Default setting should be **1 block/second** but this speed should be **adjustable mid play**.   
![[blocks_falling.png]]

#### Stopping of movement
When a block reaches the bottom of the board and **tries to move** outside of the board or into a space occupied by another block, then it stops moving. Only movement down can stop a block.
![[block_movement_stops.png]]![[moving_stop_on_block.png]]

#### Block spawn
When there is no moving block to be moved when it is time to move it, a new moving block will be spawn at the **top middle** of the board. If the block cannot fit perfectly into the middle position, it will be spawn on the right side of the middle position.![[block spawn.png]]
Which block is to be spawn is chosen randomly from all available options. See Block types bellow. 
