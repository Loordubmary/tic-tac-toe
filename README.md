# Simple Tic Tac Toe Game using JQuery

This is help to know how to make a game steps as an algorithm and how to convert the algorithm in real time application.

# Index

1. Algorithm of Tic Tac Toe
2. Implement via Jquery

# Algorithm

Before implementing the algorithm, we know about how to play the game and what are the roles are there.

## Outline of the game

```
 -----------------
|  +  |  +  |  +  |
 -----------------
|  +  |  +  |  +  |
 -----------------
|  +  |  +  |  +  |
 -----------------
```

The above is a playground of the game. The game platform divided into '9' tiles. The '+' is denoted to the tiles is now empty or ready to fill.

The game structure is as follows,

1. This is Two player game.
2. The player's chances is 5:4. First player has one more filling option when compared to the second player.
3. The player keys are 'O' and 'X'. [If you set any other play key's instead of 'O' and 'X']

The game rule is as follows,

1. The first user put 'O' symbol in any of one tiles of the game.
2. The second user put 'X' symbol in any other tiles of the game. 
3. The condition is the player should not replace the keys and they should not rewrite the key if the tiles is already filed.
4. The game contains only '9' option to filling the game tiles.
5. WIN: which player is first fill one row using their key like 'O' or 'X'(vertically, horizontally or diagonally), who is the winner of the game.
6. WINNING CHOICE: The game totally have a '8' chance to win the game.

The demo of game play is as follows,

### Demo - 1:

```
 -----------------		  -----------------	  -----------------	   	-----------------
|  +  |  +  |  +  |              |  O  |  +  |  +  |     |  O  |  +  |  +  |           |  O  |  O  |  +  |
 -----------------		  -----------------	  -----------------	   	-----------------
|  +  |  X  |  +  |              |  +  |  X  |  +  |     |  +  |  X  |  +  |           |  +  |  X  |  +  |
 -----------------		  -----------------	  -----------------	   	-----------------
|  +  |  +  |  +  |              |  +  |  +  |  +  |     |  X  |  +  |  +  |           |  X  |  +  |  +  |
 -----------------		  -----------------	  -----------------	        -----------------

  Player 1			   Player 2	 	   Player 1		         Player 2
```

```
 -----------------
|  O  |  O  |  X  |
 -----------------
|  +  |  X  |  +  |
 -----------------
|  X  |  +  |  +  |
 -----------------

 	Player 1
```

In demo-1 the game is won by player 1. Because the player fill all tiles in the diagonal row with his/her play key 'X'.

### Demo - 2:

```
 -----------------		  -----------------	  -----------------	   	-----------------
|  O  |  +  |  +  |              |  O  |  +  |  +  |     |  O  |  +  |  +  |           |  O  |  X  |  +  |
 -----------------		  -----------------	  -----------------	   	-----------------
|  +  |  +  |  +  |              |  X  |  +  |  +  |     |  X  |  O  |  +  |           |  X  |  O  |  +  |
 -----------------		  -----------------	  -----------------	   	-----------------
|  +  |  +  |  +  |              |  +  |  +  |  +  |     |  +  |  +  |  +  |           |  +  |  +  |  +  |
 -----------------		  -----------------	  -----------------	   	-----------------

  Player 1			   Player 2	 	   Player 1		         Player 2
```

```
 -----------------		  -----------------	  -----------------	   	-----------------
|  O  |  X  |  O  |              |  O  |  X  |  O  |     |  O  |  X  |  O  |           |  O  |  X  |  O  |
 -----------------		  -----------------	  -----------------	   	-----------------
|  X  |  O  |  +  |              |  X  |  O  |  +  |     |  X  |  O  |  +  |           |  X  |  O  |  +  |
 -----------------		  -----------------	  -----------------	   	-----------------
|  +  |  +  |  +  |              |  +  |  +  |  X  |     |  +  |  O  |  X  |           |  X  |  O  |  X  |
 -----------------		  -----------------	  -----------------	   	-----------------

  Player 1			   Player 2	 	   Player 1		         Player 2
```

```
 -----------------
|  O  |  X  |  O  |
 -----------------
|  X  |  O  |  O  |
 -----------------
|  X  |  O  |  X  |
 -----------------

 	Player 1
```

In demo-2 the game is a draw. Because no one fill the row with unique play key.

## Algorithm

1. Initialize first='O', second = 'X', win = '', count = 1
2. Set all tiles value = '+'
3. If the player click the tiles,
	- To check the current tiles is empty or not and win == '' and count < 10 (Total tiles is 9, if you can use `count <= 9` instead)
		- if the tiles is empty put the player play key. (if the turn is `first` put 'O' else put 'X')
			- if the count >= 5,
				- check success ratio. Because the count is less than 5, the possible of winning ratio is 0. So we calculate winning ratio after '5'.
					- The success ratio is `true` to print who are winner of the game.
		- if the tiles is not empty, show error message.
4. The step 3 process continues until the count > 9 or count = 10.
5. If the count > 9 or count = 10, the success ratio is not `true`. To print `the game is draw`.
6. Stop the game

# Implement via Jquery
