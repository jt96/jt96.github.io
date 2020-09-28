---
layout: post
title: Flappy Bird Clone
excerpt: "A clone of the popular game Flappy Bird written in Python using the pygame module"
categories: [python, game]
comments: true
image:
  feature: #
  preview: https://i.postimg.cc/ZnnHvtwQ/preview.png
  credit: Jackie Trenh
  creditlink: #
---

The goal of this project was to broaden my knowledge on python and build experience in programming with the language and I thought making a game would be a great way to do just that. I wanted to dive right into working on the game instead of spending too much time thinking of what game to create so I decided to make a clone of the popular game Flappy Bird.

The first thing I needed to do was get my game window up and running with my desired background image after intalling the pygame module.

<img align="left" src="https://i.postimg.cc/L6tHFbfF/bgd.png">
<br clear="all" /><br clear="all" />

Now to get my bird and pipes into the game.

<img align="left" src="https://i.postimg.cc/05fstwq9/birdpipes.png">
<br clear="all" /><br clear="all" />

I decided on creating a list of pipes so I could have better control over each of their values in a single variable instead of multiple variables. I used the random module to randomize the pipe's y-values so the pipe heights are always changing. Now I have to figure out how to add movement into my game. For my bird, I had its y-value constantly increasing making the bird "fall" and set pressing the spacebar to decrease its y-value by a specified amount to imitate "flapping". For my pipes, I had each pipe's x-value in the list constanstly decreasing so it moves left. The problem now is my pipes are gone after they leave the screen so I needed a way to bring my pipes back after they disappear. This was done with an if statement that checks if the pipe's x-value has decreased to a certain amount indicating it has left the screen and the pipe would be brought back to the right of the last pipe in a constant loop.

Success!

<img align="left" src="https://i.postimg.cc/J4bgPyHR/looppipes.png">
<br clear="all" /><br clear="all" />

Next step was creating a method of tracking the score. I used a counter variable that incremented the score by 1 whenever the bird "passes" the midpoint of a pipe and displays the score at the top left of the screen.

<img align="left" src="https://i.postimg.cc/q7B1H380/gameplay.png">
<br clear="all" /><br clear="all" />

The final step was to implement collision detection. How does the game know when the bird has hit a pipe? This part wasn't too bad, I created a collision checker function that returns True if the bird's y-value becomes less than or greater than a top and bottom pipe's y-value while the bird's x-value was a number in between a pipe's x-value and the x-value + the pipe's width. Once that was working, I added a game over display with the options of restarting or quitting whenever the player loses. Restarting sets all the variable values to the initial values of the game and quitting exits the game.

<img align="left" src="https://i.postimg.cc/q7YyDhw1/gameover.png">
<br clear="all" /><br clear="all" />

Adding a pause function in case players needed to pause the game.

<img align="left" src="https://i.postimg.cc/QxkgNMNM/paused.png">
<br clear="all" /><br clear="all" />


Overall, I learned that a lot goes into creating games, even simple games such as this one. There are many aspects of a game that one needs to consider and factor into their program such as the amount of pixels wide/tall an object in the game is and how fast an object moves so that playing the game feels natural. After finishing this project, there are still many things I'd like to add/change in the game. I did not get to work with pygame's built in clock object and a better looking UI for the game over menu instead of displaying just text would be nice. Perhaps using a sprite and adding in animations for the bird flapping. I am looking forward to implementing those in my next game project. Thank you for reading.

<br clear="all" /><br clear="all" /><br clear="all" />
Source code can be found <a href="https://github.com/jt96/flappy_bird_clone">here</a>.
