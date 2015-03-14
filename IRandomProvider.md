# Introduction #

The first step when the game starts it's to choose the player who will start first. There are 3 methods to choose the player:

  * You call `startGame` in the `MastermindGame` class without any arguments, and a player will be chosen for you using the .Net `Random` class
  * You call `startGame(Player)`, with the player you want to start the game
  * You create a `RandomProvider` which generates a random number for use in the decision

So, a `RandomProvider` let's you create your own random number generator with your rules

# Details #
When using a `RandomProvider`, the method `generateRandom` is called. your `RandomProvider` must return an integer. At this time, and since there are only two players, the following occurs:

  * If the number is odd, the player1 will be the first, otherwise (even number), the player2 will take the first turn.

Note: following the actual implementation, 0 (zero) will count as a even number.