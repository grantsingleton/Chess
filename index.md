## Description
This is a fully functional chess game that can be played over a network between two humans, a human and a computer, or computer vs. computer. It can also be played locally. It is written in Java. Java Swing is used as the graphics package for the GUI build. Java Sockets are used for client-server communication which enables the game to be played over a network. This game was developed by a team of 4 students using the Agile development process. The team consisted of myself, Joshua Anderson, Lily Nguyen, and Lucas Crockett. I built the GUI, move logic, and the client-server model. Lucas wrote the move validation functions and pawn upgrades, as well as performing final debugging and testing. Lily designed the menu, and performed final testing, and Joshua programmed the AI.

## Tools
* Java Swing 
* Object Oriented Programming 
  * Inheritance
  * Polymorphism
* Agile Software Development Process

## Walkthrough of the UI

### Start the Game 

![start](./pages-images/main.PNG)

### Choose Mode and Server

In the next screen, the player chooses a mode of play, and then is asked if they would like to host the server.

![server-select](./pages-images/server-select.PNG)

### Enter the Game

The board displays, and tells the user which color pieces they are (this is decided by who joins the game first).

![board](./pages-images/board.PNG)

### Play
 
Players then take turns playing the game!

![board-2](./pages-images/board-2.PNG)

## Design

### The Board

The board was designed using the Java Swing Package. A grid of JButtons are used to make the board. 

```java
		// Build the board
		for (int i = 0; i < 8; i++) {
			for (int j = 0; j < 8; j++) {
				tiles[i][j] = new JButton();
				if ((i + j) % 2 != 0) {
					tiles[i][j].setBackground(maroon); // gigem
				} else {
					tiles[i][j].setBackground(white);
				}
				space.add(tiles[i][j]);

				// Associate the action listener with each tile
				tiles[i][j].addActionListener(handleClick);
			}
		}
```
