# Simple Tic Tac Toe Game using JQuery

This is help to know how to make a game steps as an algorithm and how to convert the algorithm in real time application.

# Index

1. Algorithm of Tic Tac Toe
2. Implementation via Jquery

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

# Implementation via Jquery

Add the below code in your html,

```
<table id="game-platform">
	<tr  class="game-row">
		<td class="game-row-button" colspan="3"><p>Match</p><p id="game-result"></p></td>
	</tr>
	<tr class="game-row">
		<td class="game-row-td row-num-1">+</td>
		<td class="game-row-td row-num-2">+</td>
		<td class="game-row-td row-num-3">+</td>
	</tr>
	<tr class="game-row">
		<td class="game-row-td row-num-4">+</td>
		<td class="game-row-td row-num-5">+</td>
		<td class="game-row-td row-num-6">+</td>
	</tr>
	<tr class="game-row">
		<td class="game-row-td row-num-7">+</td>
		<td class="game-row-td row-num-8">+</td>
		<td class="game-row-td row-num-9">+</td>
	</tr>
	<tr class="game-row">
		<td class="game-row-button" colspan="3"><button class="game-restart">RESTART</button></td>
	</tr>
</table>

```

This code is help to create user view of the game. 

If you can add below css code for neet view of game playground.

```
body {
	background-color: #f3f1f0;
}
#game-platform {
	position:fixed;
	top: 50%;
	left: 50%;
	width:30em;
	height:18em;
	margin-top: -10em;
	margin-left: -25em;
	background-color: #f3f3f3;
}
.game-row-td {
	border: 1px solid #c0c0c0;
	text-align: center;
}
.game-row-button {
	border: 1px solid #c0c0c0;
	text-align: center;
}
```

The below code is to add your script function. This is the heart of your program.

```
var first = 'O';
var second = 'X';
var count = 1;
var values = [];
var win = '';
$(document).ready(function(){
	$('.game-restart').click(function(){
		$('.game-row-td').text('+');
		count = 1;
		win = '';
		$('#game-result').html('');
	});
	$('.game-row-td').click(function(){
		if($(this).text() == '+' && count < 10 && win == '') {
			$('#game-result').html('');
			if(count%2 != 0) {
				$(this).text(first);
				if(count >= 5 && win == '') {
					checkSuccessRatio();
				}
				count = count + 1;
			} else {
				$(this).text(second);
				if(count >= 5 && win == '') {
					checkSuccessRatio();
				}
				count = count + 1;
			}
		} else {
			if(count < 10 && win == '') {
				$('#game-result').html('This tiles are already filed');
			} else {
				$('#game-result').html('Please restart a game. This Game is Over');
			}
		}
	});

	function checkSuccessRatio() {
		$.each(new Array(9), function(n){
		    values[(n+1)] = $('.row-num-'+(n+1)).text();
		});

		if(values[1] == values[2] && values[2] == values[3]) {
			if(values[1] != '+') { win = values[1];	}
		} else if(values[4] == values[5] && values[5] == values[6]) {
			if(values[4] != '+') { win = values[4];	}
		} else if(values[7] == values[8] && values[8] == values[9]) {
			if(values[7] != '+') { win = values[7];	}
		} else if(values[1] == values[4] && values[4] == values[7]) {
			if(values[1] != '+') { win = values[1];	}
		} else if(values[2] == values[5] && values[5] == values[8]) {
			if(values[2] != '+') { win = values[2];	}
		} else if(values[3] == values[6] && values[6] == values[9]) {
			if(values[3] != '+') { win = values[3];	}
		} else if(values[1] == values[5] && values[5] == values[9]) {
			if(values[1] != '+') { win = values[1];	}
		} else if(values[3] == values[5] && values[5] == values[7]) {
			if(values[3] != '+') { win = values[3];	}
		}

		if(win != '') {
			$('#game-result').html('The game won By '+ win);
		} else if(count == 9) {
			$('#game-result').html('The game is Draw');
		}
	}
});
```
