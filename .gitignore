import random

cards_list = [("Tiger", 200, 50), ("Unicorn", 250, 60),
              ("Dragon", 270, 80), ("Wizard", 180, 70), ("Elf", 180, 100), ("Human", 220, 90)]

total_win = 0
total_loss = 0


def battle_game():
    """battle_game function has the following features:
    1) picking player's card
    2) picking computer's card
    3) battle between the two cards

    Returns
    --------
    int
        1 if the player wins the battle, otherwise 0.
    """
    while True:  # Player selects a card
        player_choice = int(input(
            "Please pick a card from the following: 1:'Tiger', 2:'Unicorn', 3:'Dragon', 4:'Wizard', 5: 'Elf', 6:'Human': "))
        print("\n")
        if player_choice not in [1, 2, 3, 4, 5, 6]:
            print("Your selection is not valid. \n")
        else:
            player_card = cards_list[player_choice - 1]
            print("You've chosen", player_card[0], "with initial health points of", str(
                player_card[1]), "and damage points of", str(player_card[2]), "\n")
            break

    while True:  # A card is randomly chosen for the computer
        computer_card = random.choice(cards_list)
        if computer_card != player_card:
            print("Your computer has chosen", computer_card[0], "with initial health points of", str(
                computer_card[1]), "and damage points of", str(computer_card[2]), "\n")
            break

    # The system decides which card attacks first for each battle
    battle_cards = [player_card, computer_card]
    # first_card is the card that attacks first
    first_card = random.choice(battle_cards)
    battle_cards.remove(first_card)
    second_card = battle_cards[0]
    # Variable "fc_rem_hp" is created to hold first_card's remaining health points
    fc_rem_hp = first_card[1]
    # Variable "sc_rem_hp" is created to hold second_card's remaining health points
    sc_rem_hp = second_card[1]

    print("Battle will begin! The", first_card[0], "will attack first! \n")

    # A while loop is used to execute the battle and returns the battle result
    while True:
        sc_rem_hp = sc_rem_hp - first_card[2]

        print("The", first_card[0], "attacked the", second_card[0], "!\n")
        print("The", second_card[0], "has remaining health points of", str(
            sc_rem_hp), "\n")

        if sc_rem_hp <= 0 and second_card == computer_card:
            print("Woohoo! - you win! \n")
            return 1
        if sc_rem_hp <= 0 and second_card == player_card:
            print("You lost the battle! \n")
            return 0

        fc_rem_hp = fc_rem_hp - second_card[2]

        print("The", second_card[0], "attacked the", first_card[0], "!\n")
        print("The", first_card[0], "has remaining health points of", str(
            fc_rem_hp), "\n")

        if fc_rem_hp <= 0 and first_card == player_card:
            print("You have lost the battle! \n")
            return 0
        if fc_rem_hp <= 0 and first_card == computer_card:
            print("Woohoo! - you win! \n")
            return 1

# A while loop is used to call the battle_game function so that the game can be replayed


while True:

    battle_result = battle_game()

    if battle_result == 1:
        total_win += 1
    else:
        total_loss += 1

    print("---------------------- Game Dashboard ---------------------\n")
    print("       Total Wins:", str(total_win),
          "      Total Losses:", str(total_loss))
    print("\n")
    print("-----------------------------------------------------------")

    if total_loss >= 10:
        print("You have reached the maximum number of total losses. Goodbye! \n")
        break

    while True:
        replay = input("Would you like to play the game again? Y/N: ")
        if replay.lower() not in ["y", "n"]:
            print("Invalid choice! \n")
        else:
            break

    if replay.lower() == "n":
        print("Goodbye! \n")
        break
