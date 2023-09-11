# 20_questions_pyscript
20 questions game in python

# 20 questions
answers = ["pig", "apple", "wife", "Abraham Lincoln", "Keanu Reeves", "Spiderman", "potato", "dictionary",
           "battleship", "Goku", "flower", "Earth"]
counter = 1
guess = ""


def end_game():
    print("Fartface")


def get_answer():
    import random
    index = random.randint(1, 12)
    current_answer = (answers[index])
    return current_answer


def gameplay():
    counter = 1
    current_answer = get_answer()
    while counter < 21:
        print("Guess #: ", counter),
        guess = input("Enter your guess:\n ")
        if guess != current_answer:
            print("That is not the answer!\n")
            if counter < 2:
                print("Here's some hints: \n")
                for answer in answers:
                    print(str(answer))
            if counter == 5:
                print("Starts with: \n")
                start_letter = current_answer[0]
                print(start_letter)
            if counter == 10:
                print("Here's another hint:\n ")
                hint = len(current_answer)
                print(hint)
                print("characters\n")
            if counter == 15:
                last_letter = current_answer[-1]
                print("Ends in: '" + str(last_letter) + "'\n")
            counter += 1
            if counter == 21:
                print("You Lose!  The answer is: ")
                print(current_answer)
        else:
            print("That is correct! YOU WIN!")
            counter = 21


yn = (input("Do you want to play 20 questions? y or n "))
if yn == "n":
    print("Fuck you then.")

elif yn == "y":
    print("Game On!")
    gameplay()
else:
    end_game()
