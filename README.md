import re

def chatbot_response(user_input):
    user_input = user_input.lower()
    
    # Define rule-based responses
    rules = {
        r".*(hello|hi|hey).*": "Hello! How can I assist you today?",
        r".*(how are you).*": "I'm just a bot, but I'm doing great! How about you?",
        r".*(your name).*": "I'm a rule-based chatbot! You can call me ChatBot.",
        r".*(help|support).*": "Sure! Let me know what you need help with.",
        r".*(bye|goodbye).*": "Goodbye! Have a great day!",
    }
    
    # Match input with rules
    for pattern, response in rules.items():
        if re.match(pattern, user_input):
            return response
    
    return "I'm sorry, I don't understand that. Can you rephrase?"

# Running the chatbot interactively
if __name__ == "__main__":
    print("Chatbot: Hello! Type 'exit' to end the conversation.")
    while True:
        user_input = input("You: ")
        if user_input.lower() == "exit":
            print("Chatbot: Goodbye!")
            break
        response = chatbot_response(user_input)
        print(f"Chatbot: {response}")
