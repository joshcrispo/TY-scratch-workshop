# Adding a Game Over Screen
### Catch the Ball — Step 5

---

## What You Are Building

When the timer hits 0 you want a clean Game Over screen to appear in the middle of the screen showing the result. No chat bubbles — just a proper text sprite that appears when the game ends.

---

## How It Works

Instead of the ball handling the ending, you create a completely separate sprite just for the Game Over screen. The timer tells it when to appear using a broadcast — like sending a signal between sprites.

A broadcast is a message that one sprite sends and other sprites can listen for and respond to.

---

## Step 1 — Create the Text Sprite

1. Click the paintbrush icon to draw a new sprite (bottom right)
2. Select the Text tool (the T in the costume editor toolbar)
3. Choose a large font size and a colour you like
4. Type:  Time's Up!
5. Click outside the text box
6. Name this sprite GameOver in the sprite properties

---

## Step 2 — Position It Centre Screen

In the sprite properties below the stage set:
- x: 0
- y: 0

This places it in the middle of the screen.

---

## Step 3 — Add the Script to the GameOver Sprite

    When Green Flag Clicked
      hide

    When I receive (Game Over)
      show
      wait (5) seconds
      stop (all)

What this does:
- hide         →  GameOver sprite is invisible when the game starts
- When I receive (Game Over)  →  Listens for the signal from the timer
- show         →  Makes the sprite visible in the centre of the screen
- wait 5 seconds  →  Keeps it on screen for 5 seconds
- stop (all)   →  Stops everything

Where to find the blocks:
- hide / show            →  Looks (purple)
- When I receive ()      →  Events (yellow)
- wait () seconds        →  Control (orange)
- stop (all)             →  Control (orange)

---

## Step 4 — Update the Timer Script

On your Ball sprite, replace stop (all) at the end of the timer script with a broadcast:

    When Green Flag Clicked
      set (Timer) to (60)
      repeat (60)
        wait (1) seconds
        change (Timer) by (-1)
      broadcast (Game Over)

To create the broadcast:
1. Get a broadcast () block from Events (yellow)
2. Click the dropdown inside it
3. Select New Message
4. Name it Game Over

---

## Step 5 — Move the Score to the Centre

The Score variable already shows on screen during the game. You do not need to do anything special to display it at the end — it stays on screen when the game stops.

Simply click and drag the Score display on the stage to wherever you want it to appear — centre of the screen works well alongside the Time's Up message.

---

## What Happens at the End

    Timer hits 0
      →  Timer script sends broadcast (Game Over)
      →  GameOver sprite receives it and appears centre screen
      →  Score variable stays visible on screen
      →  After 5 seconds everything stops

---

## New Concept — Broadcast

A broadcast is how sprites communicate with each other in Scratch.

    one sprite sends:      broadcast (Game Over)
    another sprite hears:  When I receive (Game Over)

This keeps your scripts independent — the ball does not need to know anything about the Game Over screen. It just sends a signal and the GameOver sprite handles the rest.
