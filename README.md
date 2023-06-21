# Truth-or-dare
import random

user_input = input("Enter name: ").title()
print("Welcome " + user_input)

user_age = int(input("Enter age: "))
print("Are you " + str(user_age) + " years old?")

user_choice = input("Enter answer here: ")

choice = ["y" , "n"]

while True:
    if user_choice == "y":
        print("Loading game...")
        print("game loaded.")
        break

    if user_choice == "n":
        user_last = input("Enter age: ")
        break

    if user_choice != "y" or user_choice != "n":
        print("Quiting game..")
        quit()
   
rule = "Welcome to Truth or Dare"
print(rule)

# ask how many people are gonna be playing.
lists = [1, 2, 3, 4,]
players = ["Bob", "david", "prince", "Charlie", "vicky"]

# List of truth questions
truth_questions = [
    "What is your biggest fear?",
    "Have you ever cheated on a test?",
    "What is your most embarrassing moment?",
    "What is your guilty pleasure?",
]

# List of dare challenges
dare_challenges = [
    "Sing a song in front of everyone.",
    "Do 10 push-ups right now.",
    "Call your crush and confess your feelings.",
    "Eat a spoonful of a spicy sauce.",
]

# Function to choose a random truth question
def get_random_truth_question():
    return random.choice(truth_questions)

# Function to choose a random dare challenge
def get_random_dare_challenge():
    return random.choice(dare_challenges)

# Main game loop
while True:
    # Check if there is only one player left
    if len(players) == 1:
        print("Game over! The winner is:", players[0])
        break

  # Get the next player
    current_player = random.choice(players)
    players.remove(current_player)
    
    # Print the player's turn
    print("It's", current_player + "'s turn.")
    
    # Choose truth or dare
    choice = input("Choose truth (T) or dare (D): ")
    
    if choice.lower() == "t":
        # Get a random truth question
        question = get_random_truth_question()
        print("Truth question:", question)
    elif choice.lower() == "d":
        # Get a random dare challenge
        dare = get_random_dare_challenge()
        print("Dare:", dare)
    else:
        print("Invalid choice. Please try again.")
    
    # Ask if the player wants to continue
    continue_game = input("Do you want to continue? (Y/N): ")
    
    if continue_game.lower() == "n":
        feedback = input("Enter feedback here: ")
        print("Game over! Thanks for playing.")
        break
    
