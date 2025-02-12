# spot_painting

# Spot Painting with Python Turtle

This project demonstrates how to create a spot painting using Python's `turtle` graphics module. The code generates random colors and uses the turtle to draw colored dots in a grid pattern.

# Code First Part

The first part of the code extracts colors from an image using the `colorgram` library. Uncomment and run the code below to extract colors from an image.

```python
 import colorgram
 colors = colorgram.extract('spot_painting.jpeg', 25)
 colours = []
 for color in colors:
     r = color.rgb.r
     g = color.rgb.g
     b = color.rgb.b
     new_colour = (r, g, b)
     colours.append(new_colour)
```

# Code Second Part

The second part of the code uses the extracted colors (or predefined colors) to create a spot painting with the turtle module.

```python
import random
import turtle
from turtle import Turtle, Screen

color_list = [
    (198, 175, 119), (125, 36, 23), (187, 157, 50), (170, 104, 56), (5, 56, 83),
    (201, 216, 205), (109, 67, 85), (39, 35, 34), (84, 141, 61), (20, 122, 175),
    (111, 161, 176), (75, 38, 48), (8, 67, 47), (65, 154, 134), (132, 41, 43),
    (184, 98, 81), (183, 180, 181), (210, 200, 108), (178, 201, 186),
    (150, 180, 170), (90, 143, 158), (28, 81, 59)
]

tim = Turtle()
turtle.colormode(255)
tim.penup()
tim.hideturtle()

def draw_spot(nr):
    tim.setheading(227)
    tim.forward(250)
    tim.setheading(0)
    number_dot = 25
    for dot_count in range(1, number_dot + 1):
        colour = random.choice(color_list)
        tim.dot(25, colour)
        tim.forward(50)
        if dot_count != 25:
            if dot_count % 5 == 0:
                tim.setheading(90)
                tim.forward(50)
                tim.setheading(180)
                tim.forward(250)
                tim.setheading(0)

draw_spot(25)

screen = turtle.Screen()
screen.exitonclick()
```

# How to Run

1. Make sure you have Python installed on your system.
2. Install the required libraries by running:
   ```
   pip install colorgram.py
   ```
3. Run the Python script to see the spot painting in action:
   ```
   python spot_painting.py
   ```

# License

This project is licensed under the MIT License. See the LICENSE file for details.
