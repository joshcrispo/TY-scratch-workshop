# Adding a Countdown Timer
### Catch the Ball — Step 4

---

## What You Are Building

A 60 second countdown timer. When the timer hits 0 the game stops. The goal is to catch as many balls as possible before time runs out.

---

## What is a Variable? (Quick Recap)

Just like Score, Timer is a variable — a box that stores a number. We start it at 60 and count it down by 1 every second.

---

## Step 1 — Create the Timer Variable

1. Click on Variables (orange)
2. Click "Make a Variable"
3. Name it Timer
4. Click OK

It will appear on screen next to your Score.

---

## Step 2 — Add the Countdown Script

Click on your Ball sprite and add this as a brand new separate script (not inside your existing one):

    When Green Flag Clicked
      set (Timer) to (60)
      repeat (60)
        wait (1) seconds
        change (Timer) by (-1)
      stop (all)

Where to find the blocks:
- set () to ()      →  Variables (orange)
- repeat ()         →  Control (orange)
- wait () seconds   →  Control (orange)
- change () by ()   →  Variables (orange)
- stop (all)        →  Control (orange)

---

## How It Works

    set (Timer) to (60)       →  Timer starts at 60
    repeat (60)               →  This loop runs 60 times
      wait (1) seconds        →  Wait 1 second each loop
      change (Timer) by (-1)  →  Count down by 1
    stop (all)                →  When loop finishes, stop everything

Since it waits 1 second and counts down 1, and does this 60 times — that is exactly 60 seconds.

---

## Step 3 — Make Sure Score Resets Too

Your ball script should already have set (Score) to (0) at the top. Make sure your Timer script also has set (Timer) to (60) at the top so both reset when the green flag is clicked.

---

## Test It

Hit the green flag. You should see the timer counting down from 60 on the screen. When it hits 0 everything stops — the ball, the catcher, everything.

Your final score is however many balls you caught in 60 seconds.

---

## Challenge

Can you display a "Game Over" or "Time's Up" message when the timer hits 0?

Hint: Look at the Looks blocks (purple) — there is a block called "say"
