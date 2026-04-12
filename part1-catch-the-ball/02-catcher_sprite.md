# Adding the Catcher Sprite
### Catch the Ball — Step 2

---

## What You Are Building

You already have a ball falling from the sky. Now you need something to catch it. This could be a bowl, a cup, a paddle — anything you like. In Scratch this is called a sprite.

---

## Step 1 — Add a New Sprite

1. Click the "Choose a Sprite" button at the bottom right of the screen
2. Search for something like Bowl, Paddle, or Button
3. Click it to add it to your project
4. You will see it appear on the screen

---

## Step 2 — Position It at the Bottom

Click on your new sprite and add this script:

    When Green Flag Clicked
      go to x: (0) y: (-150)

This places the catcher near the bottom centre of the screen when the game starts.

Where to find the blocks:
- When Green Flag Clicked  →  Events (yellow)
- go to x: y:              →  Motion (blue)

---

## Step 3 — Make It Follow Your Finger or Mouse

Add this inside a forever loop so it keeps moving:

    When Green Flag Clicked
      go to x: (0) y: (-150)
      forever
        set x to (mouse x)

What this does:
- forever keeps checking your mouse/finger position non-stop
- set x to (mouse x) moves the catcher left and right to match where you are pointing

On a phone or tablet, touching the screen acts the same as moving a mouse — so this works for everyone.

Where to find the blocks:
- forever        →  Control (orange)
- set x to ()    →  Motion (blue)
- mouse x        →  Sensing (light blue)

---

## Step 4 — Make the Ball Respond to the Catcher

Go back to your Ball sprite and add this inside the forever loop:

    if <touching (your sprite name)?> then
      go to x: (pick random -200 to 200) y: (170)

Make sure you select the correct sprite name from the dropdown inside the touching block.

What this does:
- Checks every loop if the ball is touching the catcher
- If it is, the ball resets to a new random position at the top

Where to find the blocks:
- if then           →  Control (orange)
- touching ()?      →  Sensing (light blue)
- pick random       →  Operators (green)

---

## Your Full Catcher Script

    When Green Flag Clicked
      go to x: (0) y: (-150)
      forever
        set x to (mouse x)

## Your Updated Ball Script

    When Green Flag Clicked
      set (Score) to (0)
      go to x: (pick random -200 to 200) y: (170)
      forever
        change y by (-5)
        if <touching (Catcher)?> then
          go to x: (pick random -200 to 200) y: (170)
        if <y position < -170> then
          go to x: (pick random -200 to 200) y: (170)

---

## Test It

Hit the green flag and move your mouse or finger. The catcher should follow and when it touches the ball, the ball resets to the top.
