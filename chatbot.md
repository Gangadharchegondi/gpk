# Import the random module to generate random responses
import random

# Define a list of greetings and responses
greetings = ["hi", "hello", "hey", "greetings", "what's up"]
greeting_responses = ["hello", "hi there", "hi", "nice to meet you"]

# Define a list of questions and responses
questions = ["how are you", "how's it going", "what's up"]
question_responses = ["I'm doing well, thanks", "I'm good, how are you?", "Not much, just chatting with you"]

# Define a list of farewells and responses
farewells = ["bye", "goodbye", "see you later", "take care"]
farewell_responses = ["goodbye", "see you later", "have a nice day", "take care"]

# Define a function to generate responses
def generate_response(user_input):
    user_input = user_input.lower()  # Convert to lowercase for consistent matching
    if user_input in greetings:
        return random.choice(greeting_responses)
    elif user_input in questions:
        return random.choice(question_responses)
    elif user_input in farewells:
        return random.choice(farewell_responses)
    else:
        return "I'm sorry, I didn't understand what you said."

# Define a main function to run the chatbot
def main():
    print("Hi, I'm a simple chatbot. What's your name?")
    name = input()  # Get the user's name
    print(f"Nice to meet you, {name}!")

    # Loop to continue the conversation until the user says goodbye
    while True:
        print("What would you like to talk about?")
        user_input = input()  # Get user input
        if user_input.lower() in farewells:
            print(random.choice(farewell_responses))  # Say goodbye and exit
            break
        response = generate_response(user_input)  # Generate a response
        print(response)

# Run the chatbot
if __name__ == "__main__":
    main()
