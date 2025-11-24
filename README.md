🔮 Python Number Guessing Game

This is a simple, engaging command-line game written in Python where the user attempts to guess a randomly generated secret number within a fixed range (1 to 100). The game provides hints after each guess (Too High or Too Low) and tracks the number of attempts.

✨ Features

Randomized Target: A new secret number is chosen every game.

Hint System: Provides feedback to guide the player toward the correct number.

Attempt Counter: Tracks the player's performance.

Exit Command: Allows the user to quit the game gracefully by typing q or quit.

🚀 How to Run

Prerequisites

You only need a working installation of Python 3.

Execution

Save the Code: Save the code below into a file named number_guesser.py.

Open Terminal: Navigate to the directory where you saved the file.

Run the Game: Execute the script using the Python interpreter:

python number_guesser.py


🎮 How to Play

The game will prompt you to enter a guess.

Type a number between 1 and 100 and press Enter.

The game will respond with one of the following:

Too low! Try again.

Too high! Try again.

🎉 Congratulations! You guessed the number...

Keep guessing until you win or type q to quit.

🐍 Source Code

Here is the complete code for number_guesser.py:

import random

def play_guessing_game():
    """
    A simple command-line game where the user guesses a secret number.
    """
    print("Welcome to the Number Guessing Game!")
    print("I'm thinking of a number between 1 and 100.")
    print("Can you guess it in as few tries as possible?")

    # 1. Generate the secret number (the target)
    secret_number = random.randint(1, 100)
    
    attempts = 0
    # The flag controls the game loop
    is_playing = True

    # 2. Main game loop
    while is_playing:
        try:
            # Get user input and increment attempt count
            guess = input("Enter your guess: ")
            
            # Check for quit command
            if guess.lower() in ('q', 'quit'):
                print(f"Quitting game. The secret number was {secret_number}.")
                break
                
            guess = int(guess)
            attempts += 1
            
            # 3. Check the guess using conditional logic
            if guess < secret_number:
                print("Too low! Try again.")
            elif guess > secret_number:
                print("Too high! Try again.")
            else:
                # Correct guess! End the loop and print the score
                print(f"\n🎉 Congratulations! You guessed the number {secret_number}!")
                print(f"It took you {attempts} attempts to win.")
                is_playing = False # Set flag to exit the loop

        except ValueError:
            print("Invalid input. Please enter a whole number between 1 and 100, or 'q' to quit.")
        except Exception as e:
            # General error handling
            print(f"An unexpected error occurred: {e}")
            break

# Ensure the game runs when the script is executed
if __name__ == '__main__':
    play_guessing_game()


💡 Potential Enhancements

Add support for tracking and displaying high scores (lowest number of attempts).

Implement difficulty levels (allow the user to set the number range).

Introduce a limit on the number of guesses.
