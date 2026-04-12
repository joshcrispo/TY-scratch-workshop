# Scratch Concepts Used — Catch the Ball Game

A reference guide for the blocks and concepts used in building this game.

---

## Events (Yellow Blocks)

### `When Green Flag Clicked`
This is the **starting point** of your program. Nothing runs until the green flag is clicked. Think of it like pressing "Play" — the computer starts reading your instructions from this block downward.

**Used for:** Starting the ball falling when the game begins.

---

## Motion (Blue Blocks)

### `Go to x: () y: ()`
Moves the sprite to a specific position on the screen. Scratch uses a coordinate grid:
- **x** controls left/right (negative = left, positive = right)
- **y** controls up/down (negative = down, positive = up)
- The center of the screen is x: 0, y: 0

**Used for:** Placing the ball at the top of the screen at the start and resetting it when it falls off.

### `Change y by ()`
Moves the sprite up or down by a set amount each time it runs.
- Positive number = moves **up**
- Negative number = moves **down**

**Used for:** Making the ball fall by changing y by -5 repeatedly.

### `Y Position`
A reporter block (oval shaped) that tells you the current y coordinate of the sprite. You can plug this into other blocks to check where the sprite is.

**Used for:** Checking if the ball has fallen below the bottom of the screen.

---

## Control (Orange Blocks)

### `Forever`
Repeats everything inside it **endlessly** until the program stops. This is a **loop** — one of the most important concepts in programming.

Without a loop, your code runs once and stops. With `forever`, it keeps going.

**Used for:** Keeping the ball falling continuously throughout the game.

### `If <condition> Then`
This is a **conditional statement**. It checks if something is true, and only runs the blocks inside if it is.

Think of it like a decision:
> "IF the ball is below the screen, THEN reset it to the top"

If the condition is false, the blocks inside are skipped entirely.

**Used for:** Detecting when the ball reaches the bottom and resetting its position.

---

## Operators (Green Blocks)

### `Pick Random () to ()`
Generates a **random number** between two values every time it runs. Each time the ball resets, it picks a new random x position so the ball doesn't always fall in the same spot.

**Used for:** Making the ball appear at a random x position between -200 and 200.

### `() < ()`
A **comparison operator**. Checks if the value on the left is less than the value on the right. Returns true or false — this is what goes inside the `if` block's condition slot (the pointed/hexagon shaped gap).

**Used for:** Checking if `y position < -170` meaning the ball has gone below the screen.

---

## How They All Work Together

```
When Green Flag Clicked          ← Event: starts everything
  go to x: (pick random...) y: 170   ← Motion + Operator: place ball at random spot at top
  forever                         ← Control: loop forever
    change y by -5                ← Motion: ball falls
    if <y position < -170> then   ← Control + Operator: check if ball hit bottom
      go to x: (pick random...) y: 170  ← Motion + Operator: reset ball to top
```

---

## Key Programming Concepts Summary

| Concept | Scratch Block | What it does |
|---|---|---|
| Event | `When Green Flag Clicked` | Triggers the start of the program |
| Loop | `Forever` | Repeats code endlessly |
| Conditional | `If Then` | Makes decisions based on true/false |
| Operator | `Pick Random` | Generates a random number |
| Operator | `< (less than)` | Compares two values |
| Motion | `Change y by` | Moves sprite up or down |
| Motion | `Go to x: y:` | Teleports sprite to a position |
| Reporter | `Y Position` | Reads the sprite's current y coordinate |
