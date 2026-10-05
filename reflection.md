# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  (for example: "the hints were backwards").
 
The counter for the number of attempts was off by one. For example, if a user attempts their first guess the guess count would be equal to two instead of one. This does not allow the user to have the full number of guesses allowed.  

The first bug I found was the attempt count. 

The second bug I found was that the user can  keep guessing after they have won. 

The third bug I found was that the hint worked intermittently, or was inaccurate. 

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
|guess = 50 | Attempt are 0 prior to user input | Attemps are 1 before user enters any input | None |
| guess = 60 and secret = 50 | hint shows the guess is "Too High" | "The hint says "Go Higher" | None |
|  guess = 9 and secret = 50 |hint shows the guess is "Too Low" | "The hint says "Too High" | None |
`
---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion you did not accept as written (including what the AI suggested, why you rejected or changed it, and how you verified your version). It does not have to be a suggestion that was wrong: over-engineered, out of scope, harder to read, or a poor fit for this codebase all count.

For this project I used Claude Code as my AI tool. 

Claude Code alerted me that one of my initial fixes was ourside of the code block of where I needed it to be.  This was causing a new issue. If user typed "abc" used an attempt, but typing a real number does not. 
Refactoring the code with Claude allowed me to
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

I determined that my bug was fixed by using pytest. 
Out of six test, three passed and three failed. The three that passed were the bugs that I worked on with Claude Code.  
---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
 
Code updates in files like app.py can trigger automatic reruns.  This means the file will read again from top to bottom. If a user has entered a guess, their guess will not be stored by default. Sessions are needed to store the value in memory. 

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

I want to start thinking about the tests I might need when adding, updating or fixing a feature. There were several tests for a user's guess. These tests determined if the guess was "too high", "too low" or on target. 

One thing I would do differently with AI is adding stricter guidelines. I do not want to give the AI too much agency. For example, the AI should not attempt to add Streamlit into it's own enviroment. 

I think that AI generated variable names are are not exactly elegant. 