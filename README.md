The origins of Hangman are obscure meaning not discovered, but it seems to have arisen in Victorian times, ” says Tony Augarde, author of The Oxford Guide to Word Games. The game is mentioned in Alice Bertha Gomme’s “Traditional Games” in 1894 under the name “Birds, Beasts and Fishes.” The rules are simple; a player writes down the first and last letters of a word and another player guesses the letters in between. In other sources, [where?] the game is called “Gallows”, “The Game of Hangin”, or “Hanger”. 

Implementation:This is a simple Hangman game using Python programming language. Beginners can use this as a small project to boost their programming skills and understanding logic.  

The Hangman program randomly selects a secret word from a list of secret words. The random module will provide this ability, so line 1 in program imports it.
The Game: Here, a random word (a fruit name) is picked up from our collection and the player gets limited chances to win the game.
When a letter in that word is guessed correctly, that letter position in the word is made visible. In this way, all letters of the word are to be guessed before all the chances are over. 
For convenience, we have given length of word + 2 chances. For example, word to be guessed is mango, then user gets 5 + 2 = 7 chances, as mango is a five-letter word.
Example:import random

# List of words to guess
words = ["banana", "cherry", "date", "elderberry"]

# Choose a random word
word = random.choice(words)

# Create a list to store the guessed letters
guessed_letters = ["_"] * len(word)

# Create a list to store the incorrect guesses
incorrect_guesses = []

# Game loop
while True:
    # Print the current state of the word
    print(" ".join(guessed_letters))

    # Ask the player for a guess
    guess = input("Guess a letter: ").lower()

    # Check if the guess is in the word
    if guess in word:
        # Update the guessed letters list
        for i in range(len(word)):
            if word[i] == guess:
                guessed_letters[i] = guess
    else:
        # Add the guess to the incorrect guesses list
        incorrect_guesses.append(guess)
  # Check if the player has guessed the word
    if "_" not in guessed_letters:
        print("Congratulations! You guessed the word:", word)
        break

    # Check if the player has made too many incorrect guesses
    if len(incorrect_guesses) >= 6:
        print("Sorry, you didn't guess the word. The word was:", word)
        break
_ _ _ _ _
a _ _ _ _
a _ _ _ _
a _ _ _ _
a p p _ _
a p p _ _
a p p _ _
a p p _ _
Sorry, you didn't guess the word. The word was: apple
_ _ _ _ _
_ _ _ _ _
a _ _ _ _
a _ _ _ _
a _ _ _ _
a _ _ _ _
a _ _ _ _
a _ _ _ e
a p p _ e
a p p _ e
Congratulations! You guessed the word: apple
