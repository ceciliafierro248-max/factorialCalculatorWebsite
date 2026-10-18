import streamlit as st
import pandas as pd

# The meat -> The actual function calculating the factorial, uses recursion (the function calls itself over and over until the factorial is calculated)

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

# About app Sidbar
with st.sidebar:
    st.subheader("About this app")
    st.text("This tool was created by Cecilia F. as an extension of the Python Essentials Training LinkedIn Learning course.\n")
    st.markdown("*Important Note: This calculator uses recursion, so please do not type in super large numbers.*")

#First chunk of website, brief description of factorial
st.subheader("Welcome to the Factorial Calculator!", divider = 'blue')
st.text("")
st.markdown("*Before we begin...*")
st.text("Factorials are calculated using the equation below. Factorials tell us how many ways something can be arranged.")

st.latex(r'''
    x * (x - 1) * ... * 1''')

st.text("")

#Example
st.markdown("*So, the factorial of 3 would be...*")
st.text("")
st.latex(r''' 3! = 3 * (3 - 1) * (3 - 2)''')
st.text("")
st.latex(r''' 3! = 3 * 2 * 1 ''')
st.text("")
st.latex(r''' 3! = 6 ''')
st.text("")
st.text("")

st.markdown("This means that a list of three items can be arraged in **6** ways.")

st.subheader("Proof", divider= 'blue')
st.text("")
st.text("Our list is apple (🍎), orange (🍊), banana (🍌). The facorial of 3 is 6, so see what happens when we map out all the possible orders for this list.")
st.text("")

fact3 = pd.DataFrame(
    {
        "Apple First": ["🍎  🍊  🍌", "🍎  🍌  🍊"],
        "Orange First": ["🍊  🍎  🍌", "🍊  🍌  🍎"],
        "Banana First": ["🍌  🍎  🍊", "🍌  🍊  🍎"],
    },
    index=["1", "2"],
)
st.table(
    fact3,
    alt="All possible orders of the list apple, orange, and banana.",
)
st.text("")
st.markdown("As you can see there are **6** possible ways to arrange this list!")


# Change this for a chart#
#col1, col2, col3, col4, col5, col6 = st.columns(6)

#st.subheader("", divider= 'blue')
#with col1:
#    st.subheader("1", divider='blue')
#    st.text("🍎  🍊  🍌")
#with col2:
#    st.subheader("2", divider='blue')
#    st.text("🍌  🍎  🍊")
#with col3:
#    st.subheader("3", divider='blue')
#    st.text("🍊  🍎  🍌")
#with col4:
#    st.subheader("4", divider='blue')
#    st.text("🍌  🍊  🍎")
#with col5:
#    st.subheader("5", divider='blue')
#    st.text("🍊  🍌  🍎")
#with col6:
#    st.subheader("6", divider='blue')
#    st.text("🍎  🍌  🍊")

# The Calculator input, contains logic for limiting the user to 5 attempts
st.subheader("Calculator", divider = 'blue')


attempts = 0
userInput = st.text_input("")

# Fixed

if "attempts" not in st.session_state:
    st.session_state.attempts = 0

st.text("")

if st.button("Reset attempts"):
    st.session_state.attempts = 0

attempts = st.session_state.attempts
tries = str(5 - st.session_state.attempts)

if userInput == "" and attempts > 5:
    st.text("")
    st.text("You have run out of tries")

if userInput == "":
    st.text("")
    st.text("Type a number. You have " + tries + " tries left")
    st.session_state.attempts = st.session_state.attempts + 1
    st.text("You have used " + str(attempts) + " attempts.")

else:
    if attempts > 5:
        st.text("")
        st.text("You have run out of tries")

    if attempts <= 5:

        try:
            st.text("")
            number = int(userInput)
            answer = factorial(number)
            st.session_state.attempts = st.session_state.attempts + 1
            st.text("You answer is " + str(answer) + ". Type in a number, you have " + tries + " left.")
            st.text("You have used " + str(attempts) + " attempts.")
            st.text(attempts)

        except ValueError:
            st.text("")
            st.text("Uh oh! You tried to type in " + userInput + ", which is a string (aka letters) or a decimal value. Please type in an integer value.")
            st.session_state.attempts = st.session_state.attempts + 1
            st.text("You have " + tries + " left.")
            st.text("You have used " + str(attempts) + " attempts.")

        except RecursionError:
            st.text("")
            st.text("Uh oh! You tried to type in " + userInput + ", which is too large for the calculator to handle. Please type in a smaller integer value.")
            st.session_state.attempts  = st.session_state.attempts + 1
            st.text("You have " + tries + " left.")
            st.text("You have used" + str(attempts) + " attempts.")


