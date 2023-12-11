import random

def get_computer_choice():
    choices = ["rock", "paper", "scissors"]
    return random.choice(choices)

def determine_winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "Tie"
    elif (user_choice == "rock" and computer_choice == "scissors") or \
         (user_choice == "scissors" and computer_choice == "paper") or \
         (user_choice == "paper" and computer_choice == "rock"):
        return "User wins"
    else:
        return "Computer wins"

def main():
    user_score = 0
    computer_score = 0
    rounds = 3  

    for _ in range(rounds):
        user_choice = input("Enter rock, paper, or scissors: ").lower()
        while user_choice not in ["rock", "paper", "scissors"]:
            print("Invalid input. Please try again.")
            user_choice = input("Enter rock, paper, or scissors: ").lower()

        computer_choice = get_computer_choice()
        print(f"Computer chose: {computer_choice}")

        result = determine_winner(user_choice, computer_choice)
        print(f"Round result: {result}")

        if result == "User wins":
            user_score += 1
        elif result == "Computer wins":
            computer_score += 1

        print(f"Current Score - User: {user_score}, Computer: {computer_score}\n")

    if user_score > computer_score:
        print("You win the game!")
    elif user_score < computer_score:
        print("Computer wins the game!")
    else:
        print("The game is a tie!")

if __name__ == "__main__":
    main()
