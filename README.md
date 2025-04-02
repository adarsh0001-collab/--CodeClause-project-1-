# --CodeClause-project-1-
Number guessing game using python 
import random

def number_guessing_game():
    print("Welcome to the Number Guessing Game!")
    
    # Set the range for the random number
    lower_bound = 1
    upper_bound = 100
    secret_number = random.randint(lower_bound, upper_bound)
    
    attempts = 0
    max_attempts = 10  # Maximum number of attempts allowed

    print(f"I'm thinking of a number between {lower_bound} and {upper_bound}. You have {max_attempts} attempts to guess it.")

    while attempts < max_attempts:
        # Get user input
        guess = input("Enter your guess: ")
        
        # Validate input
        if not guess.isdigit():
            print("Invalid input. Please enter a valid integer.")
            continue
        
        guess = int(guess)
        attempts += 1  # Increment the number of attempts
        
        # Check if the guess is within the valid range
        if guess < lower_bound or guess > upper_bound:
            print(f"Please guess a number between {lower_bound} and {upper_bound}.")
            continue
        
        # Provide feedback on the guess
        if guess < secret_number:
            print("Too low! Try again.")
        elif guess > secret_number:
            print("Too high! Try again.")
        else:
            print(f"Congratulations! You've guessed the number {secret_number} in {attempts} attempts.")
            break  # Exit the loop if the guess is correct

    # If the player runs out of attempts
    if attempts == max_attempts:
        print(f"Sorry, you've used all your attempts. The number was {secret_number}.")

# Entry point of the program
if __name__ == "__main__":
    number_guessing_game()

