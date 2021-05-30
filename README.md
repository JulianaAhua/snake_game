# snake_game
import random
import time
import turtle

score = 0
noTimes = 0
# creating the screen
screen = turtle.Screen()
screen.title("snake by Juls")
screen.bgcolor("green")
screen.setup(width = 600, height=600)
screen.tracer(0)

# creating the snakes head
head = turtle.Turtle()
head.penup()
head.speed(0)
head.shape("square")
head.color("red")
head.goto(0,0)
head.direction = "stop"   #default direction

snake = []

# game functions
def go_up():
    if head.direction != "down":
        head.direction = "up"
def go_down():
    if head.direction != "up":
        head.direction = "down"
def go_right():
    if head.direction != 'left':
        head.direction = "right"
def go_left():
    if head.direction != "right":
        head.direction = "left"
def pause():
    head.direction = "stop"
def reset():
    head.direction = "dawo"





# to move the snake
def move():
    if head.direction == "up":
        y= head.ycor()
        head.sety(y + 20)

    elif head.direction == "down":
        y = head.ycor()
        head.sety(y - 20)

    elif head.direction == "right":
        x = head.xcor()
        head.setx(x + 20)

    elif head.direction == "left":
        x = head.xcor()
        head.setx(x - 20)
    elif head.direction == "stop":
        head.direction = "stop"

    elif head.direction == "dawo":
        head.goto(0,0)


# creating the food
food = turtle.Turtle()
food.penup()
food.speed(0)
food.shape("square")
food.color("black")
food.goto(100, 100)
food.direction = "stop"

# keyboard setup
screen.listen()
screen.onkey(go_up, "Up")
screen.onkey(go_down, "Down")
screen.onkey(go_right, "Right")
screen.onkey(go_left, "Left")
screen.onkey(pause, "p")
screen.onkey(reset, "c")

# the main game loop
while True:
    screen.update()
    if head.distance(food) < 20:
        x = random.randint(-280, 280)
        y = random.randint(-280, 280)
        food.goto(x, y)
        score = score + 5
        noTimes = noTimes + 1
        print("oga I don chop", score)
        print("Score:", score)

        # snake new body
        new_segment = turtle.Turtle()
        new_segment.penup()
        new_segment.shape("square")
        new_segment.color("yellow")
        new_segment.speed(0)

        snake.append(new_segment)

        # moving the end segments first in reverse order
    for index in range(len(snake)-1, 0,-1):
        x = snake[index-1].xcor()
        y = snake[index-1].ycor()
        snake[index].goto(x,y)
    if len(snake) >0:
        x = head.xcor()
        y = head.ycor()
        snake[0].goto(x,y)
    move()
    time.sleep(0.1)


screen.mainloop()

