# CODEALPHA-TASK3-BASIC-CHAT-BOT-
CHAT BOT AKA SanjayBot is a friendly, rule based Python chatbot designed to simulate human like conversations. It responds to greetings, answers time related questions, remembers your name, and even tells Tamil and English jokes based on user inputs.

Features
Understands greetings and casual conversation
Tells the current time
Learns and remembers the user's name
Tells random jokes
Shares fun science facts
Handles unknown inputs gracefully
Gives movie or book recommendations
Engages in mini-choices like "joke or fact?"

Tech Used
`Python 3.x`
`datetime` – for current time
`random` – for jokes/facts
Command-line interface

How to Run
1. Save the code as `chatbot.py`
2. Open your terminal or run in Jupyter Notebook
3. Run the script:

```bash
python chatbot.py
```

Start chatting with SanjayBot! Try messages like:
`hello`
`tell me a joke`
`how are you`
`what time is it`
`bye`

Sample Conversation

SanjayBot: Hello! I'm SanjayBot — your virtual assistant.
You: hi
SanjayBot: Hello there!  What’s your name?
You: Sanjay
SanjayBot: Nice to meet you, Sanjay! 
You: tell me a joke
SanjayBot: Why don't scientists trust atoms? Because they make up everything!
You: what's my name
SanjayBot: Your name is Sanjay, right? 
You: bye
SanjayBot: Goodbye! Take care 

Optional Enhancements
Add voice using `pyttsx3`
Connect to APIs for real weather/news
Turn into a GUI using `tkinter`
Use NLP libraries for smarter chat (NLTK, OpenAI, etc.)

Author
Sanjay Shriram
Python Intern – CodeAlpha
===================================================================================================================================================================Line by Line Explanation


Import Required Modules

```python
import time
from datetime import datetime
import random
```

* `time`: (optional, here for future use like pauses or delays)
* `datetime`: used to get the current system time
* `random`: for randomly selecting a joke or fact from a list

---

Function to Get Current Time

```python
def get_time():
    return datetime.now().strftime("%I:%M %p")
```

* `datetime.now()` gets the current system time
* `.strftime("%I:%M %p")` formats it like "02:35 PM"

---

 Joke Function

```python
def tell_joke():
    jokes = [
        "Why don't scientists trust atoms? Because they make up everything! ",
        "I told my computer I needed a break, and it said 'No problem — I'll go to sleep!' ",
        "Why do Python devs wear glasses? Because they can’t C! ",
    ]
    return random.choice(jokes)
```

* Stores a list of jokes
* Uses `random.choice()` to return one randomly

---

Fun Fact Function

```python
def give_fact():
    facts = [
        "Honey never spoils. Archaeologists have found 3,000-year-old honey that’s still edible!",
        "Octopuses have three hearts and blue blood!",
        "Bananas are berries, but strawberries are not!",
    ]
    return random.choice(facts)
```

* Same as jokes, but with cool facts!

---

Main Chatbot Function

```python
def chatbot():
```

* This function runs the entire conversation loop.

---

Greeting + Instructions

```python
    print("SanjayBot: Hello! I'm SanjayBot — your virtual assistant.")
    print("You can ask me things like: 'hello', 'what time is it?', 'how are you', 'bye', etc.\n")
```

* Displays a welcome message and sample commands.

---

User Name Variable

```python
    user_name = None
```

* Stores the user’s name when they tell the bot (used for memory).

---

Main Chat Loop

```python
    while True:
        user_input = input(" You: ").lower()
```

* Starts an infinite loop to keep chatting until "bye"
* Converts user input to lowercase for easier matching

---

 Exit Condition

```python
        if "bye" in user_input:
            print("SanjayBot: Goodbye! Take care ")
            break
```

* If user says "bye", chatbot responds and exits the loop

---

Greeting and Name Capture

```python
        elif "hello" in user_input or "hi" in user_input:
            print(" SanjayBot: Hello there! What’s your name?")
            if not user_name:
                user_name = input(" You: ")
                print(f"SanjayBot: Nice to meet you, {user_name}! ")
```

* If greeting detected, bot asks for your name and remembers it.

---

Time Request

```python
        elif "time" in user_input:
            print(f" SanjayBot: It's {get_time()}.")
```

* Responds with the current time using the `get_time()` function

---

Manual Name Setting

```python
        elif "my name is" in user_input:
            user_name = user_input.split("is")[-1].strip().capitalize()
            print(f"SanjayBot: Got it, {user_name}! ")
```

* User can manually tell the bot their name
* The bot splits the sentence and extracts the name after "is"

---

Ask Bot to Recall Name

```python
        elif "what's my name" in user_input and user_name:
            print(f"SanjayBot: Your name is {user_name}, right? ")
```

* If bot remembers the user’s name, it responds with it

---

Basic Mood Question

```python
        elif "how are you" in user_input:
            print(" SanjayBot: I'm doing well, thank you! How about you?")
```

* A fixed reply to the "how are you" question

---

Thanks Response

```python
        elif "thank" in user_input:
            print("SanjayBot: You're welcome! ")
```

* Handles "thanks", "thank you", etc.

---

### ➤ Tell Me a Joke

```python
        elif "joke" in user_input:
            print("SanjayBot: " + tell_joke())
```

* Calls the `tell_joke()` function and displays a random joke

---

Tell Me a Fact

```python
        elif "fact" in user_input or "interesting" in user_input:
            print(" SanjayBot: " + give_fact())
```

* Calls the `give_fact()` function to return a random fact

---

Mood Checker Path

```python
        elif "mood" in user_input or "bored" in user_input:
            print("SanjayBot: Let's cheer you up! Want a joke or a fact?")
            choice = input(" Type 'joke' or 'fact': ").lower()
```

* Offers user a choice between joke or fact
* Bot replies based on input

---

Recommendations

```python
        elif "recommend" in user_input:
            print("SanjayBot: Would you like a movie or a book recommendation?")
            rec = input("Type 'movie' or 'book': ").lower()
```

* Offers a movie or book suggestion depending on choice

---

Weather (Simulated)

```python
        elif "weather" in user_input:
            print("SanjayBot: I don't have live weather data, but it’s always sunny in Python land! ")
```

* Fun message for weather, without live API

---

Catch-All Response

```python
        else:
            print(" SanjayBot: Hmm... I didn’t understand that. Try 'joke', 'fact', 'time', or 'bye'. ")
```

* If no known input matches, bot sends a fallback reply


Run the Chatbot
```python
chatbot()
```
* This line calls the chatbot function and starts the program

Summary

memorycapable chatbot that:
* Remembers your name
* Handles general questions
* Responds with jokes, facts, and more
* Gives user-driven branching paths

  THANK YOU 

