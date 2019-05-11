# Simple Tic Tac Toe Game using JQuery

This is help to know how to make a game steps as an algorithm and how to convert the algorithm in real time application.

# Index

1. Algorithm of Tic Tac Toe
2. Implement via Jquery

# Algorithm

# Algorithm

Before implement the algorithm, we know about how to play the game and what are the roles are there.

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

The above is a play ground of the game. The game platform divided into '9' tiles. The '+' is denoted to the tiles is now empty or ready to fill.

The game structure is follows,

1. This is Two player game.
2. The player's chances is 5:4. First player have one more filling option when compared to the secound player.
3. The player keys are 'O' and 'X'. [If you set any other play key's insteed of 'O' and 'X']

The game rule is follows,

1. The first user put 'O' symbol in any of one tiles of the game.
2. The secound user put 'X' symbol in any other tiles of the game. 
3. The condition is the player should not replace the keys and they should not rewrite the key if the tiles is already filed.
4. The game contain only '9' option to filling the game tiles.
5. WIN: which player is first fill one row using their key like 'O' or 'X'(vertically, herzontaly or dinagoly), who is a winer of the game.
6. WINNING CHOICE: The game totaly have a '8' chance to win the game.

The demo of game play is follows,

### Demo - 1:

```
 -----------------		-----------------	  -----------------	    	-----------------
|  +  |  +  |  +  |	   |  O  |  +  |  +  |   |  O  |  +  |  +  |	   |  O  |  O  |  +  |
 -----------------		-----------------	  -----------------	    	-----------------
|  +  |  X  |  +  |    |  +  |  X  |  +  |   |  +  |  X  |  +  |	   |  +  |  X  |  +  |
 -----------------		-----------------	  -----------------	    	-----------------
|  +  |  +  |  +  |    |  +  |  +  |  +  |   |  X  |  +  |  +  |	   |  X  |  +  |  +  |
 -----------------		-----------------	  -----------------	    	-----------------

 	Player 1				Player 2			 Player 1					Player 2
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
 -----------------		-----------------	  -----------------	    	-----------------
|  O  |  +  |  +  |	   |  O  |  +  |  +  |   |  O  |  +  |  +  |	   |  O  |  X  |  +  |
 -----------------		-----------------	  -----------------	    	-----------------
|  +  |  +  |  +  |    |  X  |  +  |  +  |   |  X  |  O  |  +  |	   |  X  |  O  |  +  |
 -----------------		-----------------	  -----------------	    	-----------------
|  +  |  +  |  +  |    |  +  |  +  |  +  |   |  +  |  +  |  +  |	   |  +  |  +  |  +  |
 -----------------		-----------------	  -----------------	    	-----------------

 	Player 1				Player 2			 Player 1					Player 2
```

```
 -----------------		-----------------	  -----------------	    	-----------------
|  O  |  X  |  O  |	   |  O  |  X  |  O  |   |  O  |  X  |  O  |	   |  O  |  X  |  O  |
 -----------------		-----------------	  -----------------	    	-----------------
|  X  |  O  |  +  |    |  X  |  O  |  +  |   |  X  |  O  |  +  |	   |  X  |  O  |  +  |
 -----------------		-----------------	  -----------------	    	-----------------
|  +  |  +  |  +  |    |  +  |  +  |  X  |   |  +  |  O  |  X  |	   |  X  |  O  |  X  |
 -----------------		-----------------	  -----------------	    	-----------------

 	Player 1				Player 2			 Player 1					Player 2
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

In demo-2 the game is draw. Because no one fill the row with unique play key.

# Implement via Jquery
