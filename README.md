During Week 3 of #CodePlateau, our team collaborated and developed a classic snake game. While some might consider it archaic in comparison to modern, colorful video games, we had a blast creating it, and it became quite an achievement for us.

This is a simple snake game built using Python and the Turtle graphics library. The game allows the player to control a snake and eat food to grow longer while avoiding collisions with the borders or itself. Let's understand how the game was implemented and how it works:

Language Used
The game is implemented using Python programming language.

How It Works
The game screen is created using the turtle.Screen() function, with a green background and dimensions of 600x600.

The snake's head is represented by a turtle.Turtle() object, colored red, and positioned at the center of the screen. The snake's direction is initialized to "stop," meaning it doesn't move initially.

The snake's body is managed using a list named snake. The game will add new segments to this list as the snake eats food and grows.

The game functions go_up(), go_down(), go_right(), and go_left() are used to change the direction of the snake when the player presses the arrow keys.

pause() and reset() functions allow the player to pause and reset the game, respectively.

The move() function is responsible for moving the snake based on its current direction. It updates the positions of the snake's segments to mimic movement.

A food object (turtle.Turtle()) is created and positioned randomly on the screen. When the snake's head comes in contact with the food, the snake grows longer, and the player's score increases.

The game listens for specific keyboard inputs using screen.onkey() to call the corresponding movement functions.

The game enters a continuous loop (while True) where the screen updates, and the snake moves every 0.1 seconds (time.sleep(0.1)). The loop keeps the game running and responsive to user input.

How to Play
Use the arrow keys to move the snake up, down, left, or right.

Try to make the snake eat the black food on the screen.

Each time the snake eats the food, its length increases, and your score increases by 5 points.

Be careful not to collide with the screen borders or the snake's body. If you do, the game ends.

Press the "p" key to pause the game and "c" key to reset the game.

Have Fun!
Enjoy playing the snake game and see how long you can grow the snake and how high you can score! Feel free to modify the code and experiment with different features to enhance your gaming experience. Happy coding!
