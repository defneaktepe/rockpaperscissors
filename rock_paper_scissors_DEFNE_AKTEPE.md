```python
import random

choices = ["fire", "earth", "water"]

def determine_winner(player_choice, computer_choice):
    if player_choice == computer_choice:
        return "Draw"
    elif (player_choice == "fire" and computer_choice == "water") or \
         (player_choice == "water" and computer_choice == "earth") or \
         (player_choice == "earth" and computer_choice == "fire"):
        return "YOU WIN! CONGRATS!.."
    else:
        return "COMPUTER WINS!"

def play_game():
    print("WELCOME TO TRİLEMENT GAME!")
    print("Rules:")
    print("Fire evaporetes Water.")
    print("Water erodes Earth.")
    print("Earth smothers Fire.")
    print("We will play a game with those three elements. If one of us wins two times, then congratulations!")
    print("If you do not want to continue, you can choose 'no' before starting the game.")
    
game = 1

while True:
    play_game()
    response = input("Do you want to play? (yes/no): ").strip().lower()
    computer_continue = random.choice(["yes", "no"])
    
    if response=="yes" and computer_continue == "yes":
        print("Computer also wants to continue. Starting a new game!")
        print("Game is on. GOOD LUCK!")

        while True:
            player_wins = 0
            computer_wins = 0
            
            while player_wins < 2 and computer_wins < 2:
                round_number = player_wins + computer_wins + 1
                print(f"Game {game}, Round {round_number} is starting!")

                player_choice=input("Choose fire, earth, or water:").strip().lower()

                if player_choice not in choices:
                    print("Invalid choice! Please choose 'fire', 'earth', or 'water'.")
                    continue

                computer_choice = random.choice(choices)
                print(f"Computer chose:{computer_choice}")

                result = determine_winner(player_choice, computer_choice)
                print(result)

                if result == "YOU WIN! CONGRATS!..":
                    player_wins += 1
                elif result == "COMPUTER WINS!":
                    computer_wins += 1

                print(f"Player_wins: {player_wins}, Computer_wins: {computer_wins}")

            if player_wins == 2:
                print(f"You won Game {game}!")
            else:
                 print(f"Computer won Game {game}!")
            
            while True:
                continue_answer = input("Do you want to start a new game? (yes/no): ").strip().lower()
                computer_continue = random.choice(["yes", "no"])
                if continue_answer == "yes" and computer_continue == "yes":
                    print("Both you and the computer want to continue. Starting a new game!")
                    game += 1                   
                    break
                elif continue_answer == "no" or computer_continue == "no":
                    if continue_answer == "no":
                        print("You chose to stop. GAME OVER!")
                    if computer_continue == "no":
                        print("Computer chose not to continue. GAME OVER!")
                    continue
                else:
                    print("Please answer with 'yes' or 'no'")

        if continue_answer == "no" or computer_continue == "no":
            break
            
    elif response == "no":
            print("Reconnect with nature and come to play next time!")
            print("GAME OVER!")
            break
    elif computer_continue == "no":
            print("Computer chose not to continue. GAME OVER!")
            break
        
    else:
        print("Please answer with 'yes' or 'no'!")
```


```python

```
