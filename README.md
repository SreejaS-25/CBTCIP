# CBTCIP
import random

def determine_winner(player_choice, computer_choice):
    if player_choice == computer_choice:
        return "It's a tie!"
    elif (
        (player_choice == "rock" and computer_choice == "scissor") or
        (player_choice == "scissor" and computer_choice == "paper") or
        (player_choice == "paper" and computer_choice == "rock")
    ):
        return "You win!"
    else:
        return "Computer wins!"

def main():
    choices = ["rock", "paper", "scissor"]

    while True:
        print("Choose your move: (rock, paper, scissor)")
        player_choice = input().lower()

        while player_choice not in choices:
            print("Invalid input. Please choose from: rock, paper, scissor")
            player_choice = input().lower()

        computer_choice = random.choice(choices)
        print(f"Computer chose {computer_choice}")

        result = determine_winner(player_choice, computer_choice)
        print(result)

        play_again = input("Do you want to play again? (yes/no): ")
        if play_again.lower() != "yes":
            break

if __name__ == "__main__":
    main()
