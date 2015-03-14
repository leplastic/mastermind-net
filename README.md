# Introduction

Please note: This project was discontinued.

The class was written with the intention of hiding as much game logic from the developer as possible, to allow him/her creating the GUI/CLI, instead of focusing on game details.

Also, for developers who want to create a Mastermind game from scratch, but don't want to worry using dozen of classes. All the public classes were reduced to the following:

 * Mastermind: it's a factory and allows you to create the needed objects to interact with the system
 * MastermindGame: where the action happens! This class represents a game, and allows you to simulate a board. All the moves are done internally, and the final result is returned after that
 * ScoreCard: allows you to save score from all games you wish to save. Later, the scores can be retrieved as a global score from all games, or search for a individual game, and get the score 

Enumerators were designed to be informative as well. Descriptive names and rich documentation descriptions makes easier to developer to know what each option does.
Example code

    // Creates a new custom game, with human and computer as players
    // Board has 6 rows, allowing 2 pegs per row
    MastermindGame mm = Mastermind.createCustomGame("human", "computer", 6, 2);
    
    // Creates the secret combination to be guessed by human player
    PegColor[] colors = new PegColor[] { PegColor.Blue, PegColor.Cyan };
    ColoredPegRow combination = Mastermind.createCombination(colors);
    mm.setup(combination);
    
    // The setup is done, we can start the game
    mm.startGame();
    
    while (mm.Status == GameStatus.Running)
    {
          // Note that getUserGuess must be implemented by the developer
          // It must return the user guess for the current move
          ColoredPegRow userGuess = getUserGuess();
        
          // MoveResult can give you information like how many pegs had the right color or were in the correct position
          MoveResult mr = mm.doMove(e.Current);
    }
    
    // Outside the loop, means the game already ended
    if (mm.Status == GameStatus.Ended)
      MsgBox("game ended!");

When the game ends, it's not possible to do more moves, but there is a lot of information that MastermindGame? classe can still provide, such as:

 * Time statistics
 * The winner of this match
 * Save the players victory in the ScoreCard? 
