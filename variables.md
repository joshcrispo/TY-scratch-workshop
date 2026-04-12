# Adding a Score
### Catch the Ball — Step 3

---

## What is a Variable?

A variable is like a box that stores a value. You give it a name and you can change what is inside it at any time.

In this game we use a variable called Score to keep track of how many balls the player has caught.

> Think of it like a scoreboard — it starts at 0 and goes up each time you catch the ball.

---

## Step 1 — Create the Variable

1. Click on Variables in the block categories (orange)
2. Click "Make a Variable"
3. Type Score as the name
4. Click OK

You will see the Score appear on the screen automatically in the top left corner. You can drag it anywhere you like.

---

## Step 2 — Reset the Score at the Start

At the top of your Ball sprite script, add this right after "When Green Flag Clicked":

    set (Score) to (0)

This makes sure the score starts at 0 every time you press the green flag. Without this, the score would carry over from the last game.

Where to find it:
- set () to ()  →  Variables (orange)

---

## Step 3 — Add a Point When the Ball is Caught

Find the part of your ball script where it touches the catcher. Add this inside that if statement:

    if <touching (Catcher)?> then
      change (Score) by (1)
      go to x: (pick random -200 to 200) y: (170)

The order matters here — change the score first, then reset the ball.

Where to find it:
- change () by ()  →  Variables (orange)

---

## Your Updated Ball Script

    When Green Flag Clicked
      set (Score) to (0)
      go to x: (pick random -200 to 200) y: (170)
      forever
        change y by (-5)
        if <touching (Catcher)?> then
          change (Score) by (1)
          go to x: (pick random -200 to 200) y: (170)
        if <y position < -170> then
          go to x: (pick random -200 to 200) y: (170)

---

## Test It

Hit the green flag and catch the ball. Each time you catch it the score should go up by 1. Press the green flag again and it should reset back to 0.
