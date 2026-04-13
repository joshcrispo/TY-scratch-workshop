### Dodge The Sharky!

This main be the actual second part of the workshop.

The idea is since they were catching before now they have to do the opposite now they have to dodge.

The objective is that they have to create a new project.

In this project they will need 3 things.

1. Sprite (they control), a fish
2. Sprite (they have to dodge)
3. Sprite (that hides then shows game over)

#### Concepts:

They have already learned most of the concepts from the last workshop. There won't be anything new hear.

This will utilise:

- Events
- Looks
- Motion
- Variables
- Broadcasting

### Steps

#### Step 1: Create their sprite (Fish)

The fish will spawn from near the top of the screen but the idea is that it will constantly fall, they already know this from last part.

It will be a forever loop and decreasing Y axis

But they have to be able to go up so there needs to be an if block that if they press a button ideally a mouse click, for the phone it will go up. This is how they control it, the Fish will stay in the same X-axis in the XY plane.

Now that they have sorted that out comes step 2.

#### Step 2: Create enemy sprite (shark)

The shark will come from the edge of the screen going from right to left.

It will be a forever loop and decreasing X axis, but if the shark reaches a certain X axis value then they should be moved to the right side again.

The shark should spawn randomly in whatever Y position can be top bottom or wherever. The shark will do something like so

|-------------------|
| <- Shark |
| Fish |
| |
|-------------------|

V

|-------------------|
| <- Shark |
| Fish |
| |
|-------------------|

V

|-------------------|
| |
| Fish |
| <- Shark |
|-------------------|

Graph didnt work ^ lol but yo get the idea, I hope

#### Step 3: Add Contact & Broadcast

The 3rd Sprite will be created as text when they Flag is click this should be hidden, and when it receives a broadcast only will it show, game over.

Thats the baseline, if Sprite (fish) touches Sprite (shark) then game should end, by that I mean the a broadcast should be send.

The broadcast will trigger and Sprite 3, game over TEXT will show.
