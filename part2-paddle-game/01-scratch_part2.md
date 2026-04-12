# Part 2 — 1v1 Paddle Game
### Building on top of Catch the Ball

---

## Overview

You already have a working game. Now you are going to transform it into a 2 player competitive game. Two paddles, one ball, and if you miss — the other player scores.

---

## What Changes From Part 1

    Keep:       The ball sprite
    Keep:       The bottom paddle (becomes Player 1)
    Keep:       Score variable (becomes Player 1 Score)
    Change:     Ball no longer resets when touching a paddle — it bounces
    Change:     Ball moves diagonally, not just straight down

---

## What Gets Added

    New sprite:     A second paddle at the top (Player 2)
    New variable:   Player 2 Score
    New logic:      Ball bounces off left and right walls
    New logic:      Ball bounces off both paddles
    New logic:      Ball goes past bottom = Player 2 scores
    New logic:      Ball goes past top = Player 1 scores

---

## New Concept — Bouncing

To make the ball bounce you need two new variables:

    x speed   →  controls how fast the ball moves left or right
    y speed   →  controls how fast the ball moves up or down

Instead of change y by -5 (always falling), the ball now uses:

    change x by (x speed)
    change y by (y speed)

When the ball hits a wall or paddle, you flip the direction by multiplying the speed by -1.

    Example:
    x speed starts at 5  →  ball moves right
    hits right wall      →  set x speed to -5
    ball now moves left

This is the key idea behind bouncing.

---

## Controls — Same Device 1v1

    Player 1 (bottom paddle):   A key = move left,  D key = move right
    Player 2 (top paddle):      Left arrow = move left,  Right arrow = move right

---

## Player 1 Paddle Script

Replace the old mouse following script with this:

    When Green Flag Clicked
      go to x: (0) y: (-150)
      forever
        if <key (a) pressed?> then
          change x by (-10)
        if <key (d) pressed?> then
          change x by (10)

---

## Player 2 Paddle Script

Add a new sprite at the top and give it this script:

    When Green Flag Clicked
      go to x: (0) y: (150)
      forever
        if <key (left arrow) pressed?> then
          change x by (-10)
        if <key (right arrow) pressed?> then
          change x by (10)

---

## Ball Script — Key Changes

First create two new variables:
1. Go to Variables → Make a Variable → name it x speed
2. Go to Variables → Make a Variable → name it y speed

Then delete your old ball script and replace it with this:

    When Green Flag Clicked
      set (Player 1 Score) to (0)
      set (Player 2 Score) to (0)
      set (x speed) to (5)
      set (y speed) to (5)
      go to x: (0) y: (0)
      forever
        change x by (x speed)
        change y by (y speed)
        if <touching (Paddle)?> then
          set (y speed) to (5)
        if <touching (Paddle2)?> then
          set (y speed) to (-5)
        if <(x position) > (230)> then
          set (x speed) to ((x speed) * (-1))
        if <(x position) < (-230)> then
          set (x speed) to ((x speed) * (-1))
        if <(y position) < (-170)> then
          change (Player 2 Score) by (1)
          go to x: (0) y: (0)
          set (y speed) to (5)
        if <(y position) > (170)> then
          change (Player 1 Score) by (1)
          go to x: (0) y: (0)
          set (y speed) to (-5)

Important: Make sure the names inside the touching blocks match your actual sprite names exactly.

Where to find x speed and y speed:
- They will appear in the Variables section (orange) after you create them
- Drag them into the blocks the same way you drag Score

---

## New Concepts Summary

    Concept             What it does
    ---------------     -------------------------------------------
    x speed variable    Stores left/right direction of the ball
    y speed variable    Stores up/down direction of the ball
    Multiplying by -1   Flips direction to create a bounce effect
    Two score vars      Each player has their own score tracked
    Edge detection      Checks if ball passes top or bottom edge

---

## Progression for This Part

    Step 1 (prompt only):   "Add a second paddle for Player 2 at the top"
    Step 2 (prompt only):   "Make the ball bounce off the paddles and walls"
    Step 3 (prompt only):   "Give each player their own score"
    Step 4 (prompt only):   "What happens when a player misses the ball?"
    Step 5 (open):          "Make it your own"

---

## Challenge Extensions (Fast Finishers)

- First to 5 points wins — show a winner message
- Ball speeds up every time it bounces off a paddle
- Add a centre line to make it look like Pong
- Add sound effects when the ball bounces
- Add a countdown before the game starts
