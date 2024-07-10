Complete Explanation Guide.

1. *Import Required Modules*:
   - random: Used to generate a random number within the specified range.
   - math: Used to calculate the maximum number of guesses using the logarithm function.

   
   import random
   import math
   

2. *Define the Game Function*:
   - Create a function called number_guessing_game that encapsulates all the logic for the game.

   
   def number_guessing_game():
   

3. *Get User Input for Range*:
   - Prompt the user to enter the lower and upper bounds of the range.
   - Convert the inputs to integers and store them in lower_bound and upper_bound variables.

   
   lower_bound = int(input("Enter the lower bound: "))
   upper_bound = int(input("Enter the upper bound: "))
   

4. *Generate a Random Number*:
   - Use random.randint(lower_bound, upper_bound) to generate a random number within the specified range.
   - Store this number in the variable random_number.

   
   random_number = random.randint(lower_bound, upper_bound)
   

5. *Calculate Maximum Number of Guesses*:
   - Use the formula \( \lceil \log_2(\text{upper_bound} - \text{lower_bound} + 1) \rceil \) to calculate the maximum number of guesses.
   - This ensures the user has enough attempts to guess the number.
   - Store this value in max_guesses.

   
   max_guesses = math.ceil(math.log2(upper_bound - lower_bound + 1))
   

6. *Inform User of the Number of Attempts*:
   - Print a message informing the user of the number of attempts they have.

  
   print(f"You have {max_guesses} attempts to guess the number between {lower_bound} and {upper_bound}.")
   

7. *Initialize Guess Counter*:
   - Initialize a counter guess_count to keep track of the number of guesses the user has made.

  
   guess_count = 0
   

8. *Start the Guessing Loop*:
   - Use a while loop that continues until the user has used all their attempts (guess_count < max_guesses).

   
   while guess_count < max_guesses:
   

9. *Prompt User for a Guess*:
   - Within the loop, prompt the user to enter their guess.
   - Convert the guess to an integer and store it in the variable guess.

  
   guess = int(input("Enter your guess: "))
   

10. *Increment Guess Counter*:
    - Increment the guess_count by 1 each time the user makes a guess.

    
    guess_count += 1
    

11. *Provide Feedback on Guess*:
    - Check if the guess is higher than the random number and provide feedback if it is.
    - Check if the guess is lower than the random number and provide feedback if it is.
    - If the guess is correct, print a congratulatory message and break out of the loop.

    
    if guess > random_number:
        print("Try Again! You guessed too high.")
    elif guess < random_number:
        print("Try Again! You guessed too small.")
    else:
        print("Congratulations! You guessed the number correctly.")
        break
    

12. *End of Loop Check*:
    - After the loop ends, check if the user has exhausted all guesses without guessing correctly.
    - If so, print a "Better Luck Next Time!" message.
    - If the user guessed correctly within the allowed attempts, print a congratulatory message with the number of tries.

    
    if guess_count == max_guesses and guess != random_number:
        print("Better Luck Next Time! You've used all your guesses.")
    elif guess == random_number and guess_count <= max_guesses:
        print(f"Congratulations! You guessed the number in {guess_count} tries.")
    

13. *Run the Game*:
    - Call the number_guessing_game function to start the game.

    
    number_guessing_game()
    


