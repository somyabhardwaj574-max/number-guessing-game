# number-guessing-game
system will guess a no. between 1 and 100 automatically you will have to guess it in lowest attempts by just knowing about guess if it is too high or low  
import random

def play_guessing_game():
    print("Welcome to the Number Guessing Game!")
    print("I'm thinking of a number between 1 and 100.")
    print("Can you guess it in as few tries as possible?")

    secret_number = random.randint(1, 100)
    
    attempts = 0
    is_playing = True
    while is_playing:
        try:
            guess = input("Enter your guess: ")
            if guess.lower() in ('q', 'quit'):
                print(f"Quitting game. The secret number was {secret_number}.")
                break
                
            guess = int(guess)
            attempts += 1
            if guess < secret_number:
                print("Too low! Try again.")
            elif guess > secret_number:
                print("Too high! Try again.")
            else:
                print(f"\n🎉 Congratulations! You guessed the number {secret_number}!")
                print(f"It took you {attempts} attempts to win.")
                is_playing = False 

        except ValueError:
            print("Invalid input. Please enter a whole number between 1 and 100, or 'q' to quit.")
        except Exception as e:
            print(f"An unexpected error occurred: {e}")
            break
if __name__ == '__main__':
    play_guessing_game()
