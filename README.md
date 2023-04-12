import random
import time

# Score
score_player = 0
score_bot = 0
# Creating a card deck

all_carts = [2, 3, 4, 5, 6, 7, 8, 9, 10, 10, 10, 10, 10, 11] * 4
all_suits = ['hearts♥️', 'spades♣️', 'diamonds♦️', 'clubs♣️ ']

# initial message                                                                                                                                                                                                       `
print("Do you want to play in blackjack? \nif you want, press Enter")
input()

# Dealing the first two cards to the player

score_carts = random.choice(all_carts)
suits_s = random.choice(all_suits)
print(score_carts)
print("You took a card,it a:", score_carts)
score_player += score_carts
print("Your score is", score_player)
print("Your suit is", suits_s)
score_carts = random.choice(all_carts)
print("Your score is", score_player)

# Cycle

while True:

    if score_player == 21:
        print("No more cards needed,yo have 21")
        print("Bot turn")
        time.sleep(3)

        while True:
            if score_bot > 21:
                print("bot lost. \nbecause he has", score_bot, "points, but you have", score_player)
                input("Press enter, to close")
                exit(0)
            elif score_bot < 17:
                print("Bot takes a card")
                score_carts = random.choice(all_carts)
                suits = random.choice(all_suits)
                print("Bot dropped", score_carts,suits_s,'suit' "points.")
                score_bot += score_carts
                print("Bot has", score_bot, "points")
                time.sleep(3)
            elif score_bot > score_player:
                print("Bot win\nbecause he has", score_bot, "points, but you have", score_player,
                      "Dont get upset. Try again")
                input("Press Enter, to close")
                exit(0)
            elif score_bot < score_player:
                print("You win!\nBecause the bot has", score_bot, "points and you have", score_player,
                      "Congratulations")
                input("press Enter, to close")
                exit(0)

    # If a player scores more than 21 points from the first two cards, player is lost.
    if score_player > 21:
        print("You lost  because you scored over 21")
        print("Try your attempt another time")
        input("Press Enter, to close window")
        break

    # if player score less than 21 from first two card, ask

    yes_or_no = input("Will you draw a card?\n input 'yes', if you want to draw a card or input ('no')  if you dont want")
    if yes_or_no == 'yes':
        score_cats = random.choice(all_carts)
        suits_s = random.choice(all_suits)
        print('You took a card, it is a:', score_carts,suits_s,)
        score_player += score_carts
        print("Your score is", score_player)
        print("Your suit is", suits_s)


    # If player refuses to take new card
    if yes_or_no == 'no':
        print("Your score is", score_player, 'points')
        print("Bot turns")
        time.sleep(3)

        # writing the bot algoritm

        while True:
            if score_bot > 21:
                print("You are win\n Because bot has", score_bot, 'points, but you have', score_player)
                input("Press Enter, to close")
            elif score_bot < 17:
                print("Bot takes a card")
                score_carts = random.choice(all_carts)
                suits_s = random.choice(all_suits)
                print("Bot dropped", score_bot,suits_s,"suit","points")
                score_bot += score_carts
                print("Bot has", score_bot, 'points')
                time.sleep(3)
            elif score_bot > score_player:
                print("Bot win\nbecause he has", score_bot, 'points', 'but you have', score_player, 'points',
                      "Try again")
                input("Press Enter, to close")
                exit(0)
            elif score_bot == score_player:
                print("You have equal number of points and you a draw")
                input("Press enter, to close ")
                exit(0)
            elif score_bot < score_player:
                print("You win\nbecause bot has", score_bot, 'points', 'but you have', score_player, 'points')
                input("Press Enter,to close")
                exit(0)
