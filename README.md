
Bowling Challenge
=================

* Feel free to use google, your notes, books, etc. but work on your own
* If you refer to the solution of another coach or student, please put a link to that in your README
* If you have a partial solution, **still check in a partial solution**
* You must submit a pull request to this repo with your code by 9am Monday week

## How to use 

Listed below are the instructions I was given for this Makers Academy task. This is a task that has proved to be more difficult than first expected, but one that I have finished successfully. It challenged my ability to create an algorithm with a scoring system that relies on future values to obtain a correct output.

Bugs:
- the program does not correctly score when multiple strokes are introduced, therefore do not use this as an actual scoring card if you're good at consistently getting strikes

If you'd like to see this running for yourself, grab a copy of the repository and run the following commands 
```
# Setup our environment to use node latest version
$ nvm use node

# Run tests
$ jest

# To use the scorecard
$ node
$ const game = require('./lib/scorecard.js)

# While in node .addFrame(a,b) to add a score, .calculateScore() to calculate current score and addFrame10(a,b,c) to add the final frame
$ game.addFrame(firstRoll, secondRoll)
$ game.calculateScore()
```

## The Task

**THIS IS NOT A BOWLING GAME, IT IS A BOWLING SCORECARD. DO NOT GENERATE RANDOM ROLLS. AN ACTUAL USER INTERFACE IS OPTIONAL**

Count and sum the scores of a bowling game for one player (in JavaScript). 

A bowling game consists of 10 frames in which the player tries to knock down the 10 pins. In every frame the player can roll one or two times. The actual number depends on strikes and spares. The score of a frame is the number of knocked down pins plus bonuses for strikes and spares. After every frame the 10 pins are reset.

Start by looking in detail at the rules and the example of scoring for a complete game given below.

An example of how your code might be used could be:

```javaScript
let scorecard = new Scorecard()
scorecard.calculateScore() // returns 0
scorecard.addFrame(2, 5) 
scorecard.addFrame(3, 5)
scorecard.calculateScore() // returns 15
```

But feel free to add other methods if you think they are useful.

As usual please start by

* Forking this repo

* Using test-driven development (if you decide to write a user interface, then make sure you have looked at the chapters on mocking).

* Finally submit a pull request before Monday week at 9am with your solution or partial solution.  However much or little amount of code you wrote please please please submit a pull request before Monday week at 9am. 

___STRONG HINT, IGNORE AT YOUR PERIL:___ Bowling is a deceptively complex game. Careful thought and thorough diagramming — both before and throughout — will save you literal hours of your life.

### Optional Extras

In any order you like:

* Set up [Travis CI](https://travis-ci.org) to run your tests.
* Add [ESLint](http://eslint.org/) to your codebase and make your code conform.
* Create a UserInterface class, allowing you to run a game from the command line.

You might even want to start with ESLint early on in your work — to help you
learn Javascript conventions as you go along.

## Bowling — how does it work?

### Strikes

The player has a strike if he knocks down all 10 pins with the first roll in a frame. The frame ends immediately (since there are no pins left for a second roll). The bonus for that frame is the number of pins knocked down by the next two rolls. That would be the next frame, unless the player rolls another strike.

### Spares

The player has a spare if the knocks down all 10 pins with the two rolls of a frame. The bonus for that frame is the number of pins knocked down by the next roll (first roll of next frame).

### 10th frame

If the player rolls a strike or spare in the 10th frame they can roll the additional balls for the bonus. But they can never roll more than 3 balls in the 10th frame. The additional rolls only count for the bonus not for the regular frame count.

    10, 10, 10 in the 10th frame gives 30 points (10 points for the regular first strike and 20 points for the bonus).
    1, 9, 10 in the 10th frame gives 20 points (10 points for the regular spare and 10 points for the bonus).

### Gutter Game

A Gutter Game is when the player never hits a pin (20 zero scores).

### Perfect Game

A Perfect Game is when the player rolls 12 strikes (10 regular strikes and 2 strikes for the bonus in the 10th frame). The Perfect Game scores 300 points.

In the image below you can find some score examples.

More about ten pin bowling here: http://en.wikipedia.org/wiki/Ten-pin_bowling

![Ten Pin Score Example](images/example_ten_pin_scoring.png)

## Code Review

In code review we'll be hoping to see:

* All tests passing
* The code is elegant: every class has a clear responsibility, methods are short etc.

Reviewers will potentially be using this [code review rubric](docs/review.md).  Note that referring to this rubric in advance may make the challenge somewhat easier.  You should be the judge of how much challenge you want.
