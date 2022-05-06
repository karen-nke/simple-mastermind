import random  # Importing random module from python library


# Name & Rules for this game
print("\n                    ✰ ✰ ✰ PYTHON MASTERMIND COMPUTER GAME ✰ ✰ ✰ \n")
print(" ------------------------------Rules of this game ------------------------------\n")
print("➤ I'm thinking of a 4 color code. Try and guess what is it!")
print("➤ Try to guess the color in order as few times as possible.")
print("➤ You have only 10 attempts for each round.")
print("➤ You will get a hint after every guesses.")
print("➤ This game have 5 colors, Green, Blue, Yellow, White and Red")
print("➤ Please input G(Green), B(Blue), Y(Yellow), W(White) and R(Red).")
print("➤ Example Answer: GBGY")
print("NOTED: The color may be repeated")


# List of available colors
colors = ["G", "B", "Y", "W", "R"]
attempts = 0
game = True

# Randomise the color with repetition
color_code = random.choices(colors, k=4)
print("----------------------------------------------------------------------------------")
print("Please key in your guessed color below\n")
print(color_code)  # This line of code is just for checking, please delete this if you don't want answer to be display.
print("----------------------------------------------------------------------------------")

# Let player guess the number
while game:
    player_guess = list(input("Enter your answer: ").upper())  # .upper allows lower case
    attempts += 1

    # During the game (Check player's input)
    if len(player_guess) != len(color_code):
        print("\nYou must enter four color of your guesses. Please try again :)")
        continue
    for i in range(4):
        if player_guess[i] not in colors:
            print("\nYou had entered the wrong color. We only have green(G), blue(B), yellow(Y), white(W) and red(R).")
            print("Please try again :)")
            break

    # Compared player guesses with computer guesses

    # Determine the right color and right position
    def right_ans():
        right = 0
        for i in range(4):
            if player_guess[i] == color_code[i]:
                right += 1
        return right

    # Determine right color but wrong position
    def wrong_ans():
        check_ans = color_code[:]
        wrong = 0
        for i in range(4):
            if player_guess[i] in check_ans:
                check_ans.remove(player_guess[i])
                wrong += 1
        return wrong


    # Feedback (Hint) to user at every guesses.
    def feedback(right, wrong):

        feedback1 = str(right) + " Correct Color and Right Position "
        feedback2 = str(wrong - right) + " Correct Color but Wrong Position "
        feedback = feedback1 + "\n" + feedback2 + "\n"
        return print(feedback)


# If user guessed it correctly
    if right_ans() == 4:
        if attempts == 1:
            print("WOW! You guessed at the first attempt!")
        else:
            print("Well Done.. You needed " +str(attempts) + " attempts to guess.")
        game = False

# If user didn't guessed it correctly below 10 attempts
    if attempts >= 1 and attempts < 10 and right_ans() != 4:
        feedback(right_ans(),wrong_ans())
        print("Number of attempts used: " + str(attempts))
        print("You have", int(10 - attempts), "attempts left.\n")

# If user didn't guessed it correctly after 10 attempts
    elif attempts >= 10:
        print("Oh No! You didn't guess it right. The secret color code was:" + str(color_code) +".")
        game = False

    # Continue or not?
    while game == False:
        end_game = input("\nDo you wish to play a new round? (Please reply YES or NO)\n >> ").upper()
        attempts = 0

        if end_game == "NO":
            print("Thanks for playing the game! Bye Bye !")
            break


        elif end_game == "YES":
            game = True

            color_code = random.choices(colors, k=4)
            print("----------------------------------------------------------------------------------")
            print("So, lets play again... Guess the secret code: ")
            print("Please key in your guessed color below\n")
            print(color_code)  # Delete this if you don't want answer to be display.
            print("----------------------------------------------------------------------------------")


