# Scratch Block Reference Guide
### Catch the Ball — Workshop Handout

---

## What is a Block?

In Scratch, instead of typing code, you snap together colourful blocks — like Lego. Each block does one specific thing. When you connect them, you build a program!

---

## EVENTS (Yellow Blocks)

**When Green Flag Clicked**

This is where your program starts. Nothing happens until you click the green flag at the top of the screen. Every script needs one of these at the top.

> Think of it like a starting gun in a race — nothing moves until it goes off.

---

## MOTION (Blue Blocks)

**Go to x: ( ) y: ( )**

Moves your sprite to a specific spot on the screen. Scratch uses a grid:
- x controls left and right
- y controls up and down
- The middle of the screen is x: 0, y: 0
- Left is negative x, Right is positive x
- Up is positive y, Down is negative y

> Example: go to x: 0 y: 170 puts the sprite near the top centre of the screen.

---

**Change y by ( )**

Moves the sprite up or down by a number.
- Positive number = moves UP
- Negative number = moves DOWN

> We use Change y by -5 to make the ball fall down a little bit at a time.

---

**Y Position**

This is a reporter block — it tells you where the sprite currently is on the y axis. You can plug it into other blocks to check the sprite's position.

---

## CONTROL (Orange Blocks)

**Forever**

Repeats everything inside it over and over until the program stops. This is called a LOOP.

> Without a loop, your code runs once and stops. The forever block keeps the ball falling non-stop.

---

**If ( ) Then**

Checks if something is true. If it is, it runs the blocks inside. If not, it skips them.

This is called a CONDITIONAL — the program makes a decision.

> Example: IF the ball is below the screen, THEN move it back to the top.

---

## OPERATORS (Green Blocks)

**Pick Random ( ) to ( )**

Picks a random number between two values every time it runs.

> We use pick random -200 to 200 for the x position so the ball does not always fall in the same spot.

---

**( ) < ( )**

Checks if one number is less than another. Returns true or false. This goes inside the If block to create a condition.

> Example: y position < -170 means "has the ball gone below the bottom of the screen?"

---

## HOW IT ALL FITS TOGETHER

Here is the full script for the falling ball and what each line does:

    When Green Flag Clicked
        → Starts the program

    Go to x: (pick random -200 to 200) y: 170
        → Places the ball at a random spot near the top

    Forever
        → Starts an endless loop

        Change y by -5
            → Ball falls down a little each time

        If <y position < -170> Then
            → Checks if ball has gone off the bottom

            Go to x: (pick random -200 to 200) y: 170
                → Resets ball to a new random spot at the top

---

## QUICK REFERENCE TABLE

    Block               | Category  | What it does
    --------------------|-----------|----------------------------------
    When Green Flag     | Events    | Starts the program
    Go to x: y:         | Motion    | Moves sprite to a position
    Change y by         | Motion    | Moves sprite up or down
    Y Position          | Motion    | Reads current y position
    Forever             | Control   | Loops forever
    If Then             | Control   | Makes a decision
    Pick Random         | Operators | Generates a random number
    < (less than)       | Operators | Compares two numbers

---

*This handout is part of the Scratch Workshop — Catch the Ball Game*
