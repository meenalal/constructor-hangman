Javascript Constructor Hangman Game
--------------------------------------------------
Table of contents
--------------------------------------------------
 .Demo
 .About this project
 .Getting started
 .Clone the repository
 .Install Node.js
 .Install the dependencies
 .Starting the game
 .Playing the game
 .Technologies used to create app
 .Future code development
 .Issues
 
 -------------------------------------------------

Demo
--------------------------------------------------
Video demo: https://www.youtube.com/watch?v=3F9VjnIJ6jI&feature=youtu.be

About this project
  This project is a command line version of the classic Hangman game. This game uses similar logic to the browser-based Hangman game I created, but with this game, I created a command line version using Javascript constructor functions to create letter and word objects, the inquirer npm package to prompt users to guess a letter, and Node.js to run the Javascript code from the command line. For more information on how this project was constructed and put together, see Structure of the project.

Getting started
  To play the game from your computer and/or contribute to this project, perform the following steps:

   1.Clone the repository
   2.Install Node.js
   3.Install the dependencies
   
Clone the repository
   The first step is to clone the project repository to a local directory on your computer. To clone the repository, run the following commands:

  git clone https://github.com/philipstubbs13/constructor-hangman.git
  cd constructor-hangman
  
Install Node.js
   If you don't already have Node.js installed on your computer, you can install the latest version here: https://nodejs.org/en/.

Structure of the project
  After you clone the repository, navigate to the project root directory (constructor-hangman). The project directory structure is set up as follows:

  .Letter.js: Contains a constructor, Letter. This constructor displays an underlying character or a blank placeholder (underscore), depending on whether or not the user has guessed the letter. This constructor includes:

     1.A string value to store the underlying character for the letter.
     2.A boolean value that stores whether that letter has been guessed yet by the user.
     3.A function that returns the underlying character if the letter has been guessed, or a placeholder (underscore) if the letter has not been guessed.
     4.A function that takes a character as an argument and checks it against the underlying character, updating the stored boolean value to true if it was guessed correctly
	 
  .Word.js: Contains a constructor, Word that depends on the Letter constructor. This is used to create an object representing the current word the user is attempting to guess. The constructor includes:

     1.An array of new Letter objects representing the letters of the underlying word.
     2.A function that returns a string representing the word. This calls the function on each letter object (defined in Letter.js) that displays the character or an underscore and concatenates those together.
     3.A function that takes a character as an argument and calls the guess function on each letter object (defined in Letter.js).
	 
   .index.js: The file containing the logic for the course of the game, which depends on Word.js and:

      1.Randomly selects a word and uses the Word constructor to store it.
      2.Prompts the user for each guess and keeps track of the user's remaining guesses.

   .package.json: Lists the project dependencies (third party npm packages) and their version numbers.
   .gitignore: Any file or directory listed inside this file will not be tracked by GitHub when code is committed.
   package-lock.json: Dependency tree for the project. Lists all the dependencies and their versions.
   
Install the dependencies
--------------------------------------------------
   The following npm packages are dependencies to the project. You must install these packages in the project root directory (constructor-hangman) to be able to play Hangman from the command line.

   After you clone the repository to a local directory, change directory to the project root directory (constructor-hangman) and run the following command to install the required npm packages:

   npm install
      1.inquirer npm package (https://www.npmjs.com/package/twitter) - used to prompt users for a letter throughout the game.
      2.cli-color npm package (https://www.npmjs.com/package/cli-color) - used to add color to the game.
      3.figlet npm package (https://www.npmjs.com/package/figlet) - used to convert text into ASCII art - drawings made out of text characters.
      4.is-letter npm package (https://www.npmjs.com/package/is-letter) - used for form valiation. This package is used to check if the value the user enters is a letter (for example, "a") or not a letter (for example, "aba").
      5.boxen npm package (https://www.npmjs.com/package/boxen) - used to create boxes in terminal.
  Version information for each of these packages is available in the package.json file in the project root directory.

Starting the game
--------------------------------------------------
To start the game, run the following command from the project root directory (constructor-hangman):

node index.js
When you run this command, you will see the following screen:

$ node index.js
  _   _                                            ____
 | | | | __ _ _ __   __ _ _ __ ___   __ _ _ __    / ___| __ _ _ __ ___   ___
 | |_| |/ _` | '_ \ / _` | '_ ` _ \ / _` | '_ \  | |  _ / _` | '_ ` _ \ / _ \
 |  _  | (_| | | | | (_| | | | | | | (_| | | | | | |_| | (_| | | | | | |  __/
 |_| |_|\__,_|_| |_|\__, |_| |_| |_|\__,_|_| |_|  \____|\__,_|_| |_| |_|\___|
                    |___/
Welcome to the Hangman Game!
Theme is... Minnesota cities.
==========================================================================================================
How to play
==========================================================================================================
When prompted to enter a letter, press any letter (a-z) on the keyboard to guess a letter.
Keep guessing letters. When you guess a letter, your choice is either correct or incorrect.
If incorrect, the letter you guessed does not appear in the word.
For every incorrect guess, the number of guesses remaining decrease by 1.
If correct, the letter you guessed appears in the word.
If you correctly guess all the letters in the word before the number of guesses remaining reaches 0, you win.
If you run out of guesses before the entire word is revealed, you lose. Game over.
===========================================================================================================
You can exit the game at any time by pressing Ctrl + C on your keyboard.
===========================================================================================================
At the prompt, enter your name and press Enter.

? What is your name?
When prompted, enter Y to begin playing.

Are you ready to play? (Y/n)

Playing the game
--------------------------------------------------
When the game starts, you will be given a word and the number of letters in that word.

When prompted, try to guess a letter that is in the word.

Great! Welcome, Phil. Let's begin...
Your word contains 7 letters.
WORD TO GUESS:
You start the game with 10 guesses. If your guess is incorrect, the number of guesses remaining decreases by 1.

You guessed: Z
┌─────────────────────────────────┐
│                                 │
│   Letters already guessed:  Z   │
│                                 │
└─────────────────────────────────┘
WORD TO GUESS:
 A  A
INCORRECT!
You have 9 guesses left.
=====================================================================
If your guess is correct, the letter is added to the word.

=====================================================================
? Guess a letter: a
You guessed: A
┌───────────────────────────────────┐
│                                   │
│   Letters already guessed:  Z A   │
│                                   │
└───────────────────────────────────┘
WORD TO GUESS:
 A   A
CORRECT!
=====================================================================
If you guess all the letters in the word before the number of guesses reaches 0, you win.

WORD TO GUESS:
M A N K A T O
CORRECT!
=====================================================================
=====================================================================
YOU WON! YOU'RE A TRUE MINNESOTAN!
Wins: 1
Losses: 0
=====================================================================
Technologies used to build app
--------------------------------------------------
   1.Node.js (https://nodejs.org/en/)
   2.Javascript constructor functions

Future code development
--------------------------------------------------
1.Source code will be developed over time to handle new features.

2.The following is a list of potential feature enhancements:

   1.Create a mySQL database and create a sign up and login system that prompts users for a username and password upon loading up the app.
   2.When the user guesses a city correctly, add a fun fact about that city.
   3.Expand the game to include different categories in addition to cities. For example, Minnesota landmarks, Minnesota athletes, etc.
   4.When random word is chosen at the beginning of the game, display a hint to help the user.

Issues
--------------------------------------------------
If you find an issue while using the app or have a request, log the issue or request here. These issues will be addressed in a future code update.
