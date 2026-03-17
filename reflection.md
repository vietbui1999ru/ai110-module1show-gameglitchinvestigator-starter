# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it: the game looks fine UI wise. Main screen with input for guessing, output for guessing low, high, or correct, button to go into debug mode for extracting deterministic secret number. List button for choosing difficulty.
  
- List at least two concrete bugs you noticed at the start:
  - Guessing low and high are incorrect, flipped or just want to say "higher". Wrong guessing logic.
  - Changing difficulty doesn't change the guessing range and lives. Game configuration always stays the same.
  - Start a new game doesn't actually start a new game.
    

---

## 2. How did you use AI as a teammate?

- I used Claude as my teammate.
- I asked Claude to initialize context for the project, understand the idea of project. I asked it to analyze snippets of code that I think were missing or wrong for the guessing logic. 
- Not sure If my teammate hallucinated during this process. I have a lot of guardrails to prevent Claude to make assumptions (devil's advocate parallel teammate).
- ---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed? I decide when I play through the game itself and specifically check for the recently updated and attempted fix on the bugs.
- Describe at least one test you ran: manually, I just asked Claude what workflow I should do during the game. I also used Pytest to run tests against the guessing code logic between expected and the actual answers.
- Did AI help you design or understand any tests? How? AI helped me understand the logic of the game, nothing else as of now.

---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app: Streamlit's framework stored a randomly generated secret number for each session and kept it in memory. 
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit? Streamlit's reruns is a feature that allows you to run the same code multiple times, but it's not a good idea to use it for state management.
- What change did you make that finally gave the game a stable secret number? I modified the code to save the secret number in a variable and retrieve it from the varialbe in each session.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects? Creating unit tests.
- What is one thing you would do differently next time you work with AI on a coding task? Be more specific with the lines of code or code snippets that I want to investigate.
- In one or two sentences, describe how this project changed the way you think about AI generated code. AI can't always generate correct code until you give it detailed context and steer it in the right direction to fix or generate new code/features.
