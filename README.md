# Bulls and cows

## The game

A 1v1 game about guessing the oppenents four chosen colors.

### how to play

Each player has to pick four colors. Then over 12 laps of guessing the other player has to guess four color, after each guess the player has to write to the other player for each color if it exist out of the four colors and if it is in the right place.

# The idea

Create the bulls and cows game.

### The Game

Each of the two players chooses four colors, the goal of the player is to guess the other one colors.
The game lasts for 12 guesses and each lap the player recieves a feedback on the guess, if the color is part of the line it turns yellow or in the right place it turns green.

### The Design

each player will have a client written in C and will be connected to a python server.

#### The client - C

- get name
- list opponents
- choose or accept dual
- picker for the 4 colors the other player needs to guess.
- send the colors to the server
- send a guess of the other player to the server
- receive enemy guess
- give feedback to the other player or correct
- send the feedback
- receive feedback of your guess
- End screen

#### The server - Python

- Connect 2 players
- CHAT???
- forward guess
- forward feedback or correct

#### Protocol

- entering game game
  - announce name
  - list of names
- in game
  - guess or feedback
  - four colors

PROTOTIPE:
ENTER
GAME **msgs: 6**
you steve  
OOOO IIII OOOO IIII  
OOOO IIII OOOO IIII  
OOOO IIII OOOO IIII  
OOOO IIII OOOO IIII  
 CHAT **got feedback**
msg
test

FILES:
client: - main.c - master logic start to game and chat - game.c - main game logic and utils functions - game.h - chat.c - chat.h - ui.c - colors and general ui utils - ui.h - protocol.c - logic of recv and send to the server - protocol.h
server: - main.py - master loop - protocol.py

## Game Flow

1. user1 - enter your name
2. system - show list of players and amount of wins
3. user1 - choose rival
4. system - send game request to user2
5. user2 - accept game
6. users - choose four colors in order
7. for turn until winner
   1. users - guess
   2. system - show rival's guess
   3. users - evaluate and return rival's values
   4. if user1 or user2 recive full score: game over and winner gets a point
8. return to step 2

## Work Mile Stones

1. print loop - prints the current state of the game
   1. logic that creates string for turn with colors
   2. logic that creates string for chat
   3. logic that combines the two
2. update loop - updates according to the info from server and stuff
   1. logic that gets guesses from server
   2. logic that gets messages from server
   3. logic that sends messages to server
   4. logic that sends guesses to server
