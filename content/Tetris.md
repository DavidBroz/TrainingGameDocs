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