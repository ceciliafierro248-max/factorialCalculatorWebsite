# This is a factorial function. It's purpose is to find the factorial of positive numbers.
# The function is recursive, meaning that it calls the function within the function in order the find the factorial
# Ideas for code advancements: Go ahead and fix the none after correct when doing testFactorial and allow user to type in factorial they want in command line
# Update: Completed Ideas, now a user has 5 opportunities to type in integers of choice and learn their factorial value


def factorial(num):
    # This code does not really need to be here any more because we have a integer checker below, but I am going to keep it as a redunducy
    if type(num) != int:
        return print('Uh oh, what you typed in was not an integer. Please try again.')

    if num < 0:
        return print('Sorry, your chosen number is either a negative number, which can not be calculated by this calculator.')
    if num == 0 or num == 1:
        return 1
    if num > 1:
        result = num * factorial(num-1)
        return result

pass

# Fixed bug with the help of a search engine; substited if else for a try except.
# Try and except works by trying out the code below, but if a certain error comes up (aka ValueError in this case), it will follow the except clause
# ValueError is triggered if the user tries to type in a string (spam spam spam) or a decimal


# Gives the user 5 opportunities to utilize the calculator

a = 0
input('\n\n\n\nWelcome to the factorial calculator! Press enter to naviagte and follow the directions on screen.')
input('This tool was created by Cecilia F. as an extension of the Python Essentials Training LinkedIn Learning course.\n')
input('Before we begin, lets start by explaining what a factorial is!')
input('\nFactorials are a number * number -1 ... * 1. Factorials tell us how many ways something can be arranged. Lets look at how they are calculated!')
input('\nFactorial of 3 is equal to 3 time 2 times 1, which equals 6. This means a list of 3 items can be arranged in 6 different ways. Lets calculate some factorials!')
input('\nAn important note, this calculator uses recursion, so please do not type in large numbers.')

while a < 5:
    # Made this a string because need to catcatate later
    tries = str(5 - a)
    userInput = input('\nType in a number. You have ' + tries + ' numbers left ')

    try:
        # All values in the command line automatically import as a string, so this makes them an integer
        number = int(userInput)
        answer = factorial(number)
        a = a + 1
        print(answer)

    except ValueError:
        # Have to have this so if anyone tries to type in letters or a decimal, the program does not break.
        # Also substracted tries so the program ends
        print('Uh oh! You tried to type in a string (aka letters) or a decimal value. Please type in an integer value.')
        a = a + 1
