import random

def get_player_choice():
    choice = input("Choose stone, paper, or scissors: ").lower()
    while choice not in ['stone', 'paper', 'scissors']:
        choice = input("Invalid choice. Choose stone, paper, or scissors: ").lower()
    return choice

def get_computer_choice():
    return random.choice(['stone', 'paper', 'scissors'])

def determine_winner(player_choice, computer_choice):
    if player_choice == computer_choice:
        return "It's a tie!"
    elif (player_choice == 'stone' and computer_choice == 'scissors') or \
         (player_choice == 'paper' and computer_choice == 'stone') or \
         (player_choice == 'scissors' and computer_choice == 'paper'):
        return "Player wins!"
    else:
        return "Computer wins!"

def main():
    print("Welcome to Stone-Paper-Scissors game!")
    player_choice = get_player_choice()
    computer_choice = get_computer_choice()
    print(f"Player chose: {player_choice}")
    print(f"Computer chose: {computer_choice}")
    result = determine_winner(player_choice, computer_choice)
    print(result)

if __name__ == "__main__":
    main()
