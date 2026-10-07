# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start (for example: "the hints were backwards").

When I first ran the game, I noticed several issues. These are listed below:

1) "Normal" mode has a wider range than "Hard" mode, which doesn't make any sense
2) "Normal" modes allows more guesses than "Easy" mode, which doesn't make any sense either
3) Even when switching difficulties, the info box always mentions "Guess a number between 1 and 100"
4) At the start, the number of attempts available to the user is always 1 less than what it should be ('off-by-one' error)
5) The secret number doesn't change when switching difficulties, which is an issue if it's outside the respective difficulty range
6) When a guess is above the secret, the hint misleads you by saying that the guess is below the secret rather than above
7) When a guess is below the secret, the hint misleads you by saying that the guess is above the secret rather than below
8) If you finish one round and wish to play again, the game freezes afterwards (doesn't allow you to play again)

- Issues 1 and 2 live in app.py, specifically the 'get_range_for_difficulty' function
- Issue 3 lives in app.py, specifically line 110
- Issue 4 lives in app.py, but I'm not quite sure what is causing this error
- Issue 5 lives in app.py, specifically lines 134-138
- Issues 6 and 7 live in app.py, specifically in the 'check_guess' functions
- Issue 8 lives in app.py, but I'm not quite sure what is causing this error

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error | Suspected Code Location |
|-------|-------------------|-----------------|------------------------|-------------------------|
| Guess of 70 | "Go LOWER!" because the actual value is 36 | "Go HIGHER!" | none | app.py, check_guess |
| Guess of 32 | "Go HIGHER!" because the actual value is 36 | "Go LOWER!" | none | app.py, check_guess |                                          
| Guess of 36 | Should be able to start a new game after correct guess | Game doesn't restart after clicking the "Start new game" button | none | app.py, lines 140-145 |                                           

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). It does not have to be a suggestion that was wrong: over-engineered, out of scope, harder to read, or a poor fit for this codebase all count.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest) and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
