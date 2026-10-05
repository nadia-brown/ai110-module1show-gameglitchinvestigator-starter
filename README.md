# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- [ ] Describe the game's purpose.
  This is a guessing game. The computer generates a secret number which the user needs to guess. They are given 7 attempts. If the user guesses the number within the alloted muber of attempts they win. If the user runs out of attempts and run out of guesses they lost. 
  
- [ ] Detail which bugs you found.

The first bug is the attempt count. 

The second bug that a user can  keep guessing after they have won. 

The third bug is that the hints worked intermittently,

- [ ] Explain what fixes you applied.

The fixes applied are the attempt counter, the game ending, and the hint notification. 

The attempt counter keeps an accurate count for the number of user attempts. 

The game is disabled after a player wins. The user cannot keep playing.

 The hint notication displays a response for each guess attempt. 


## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. User enters a guess of 50
2. Game returns "Too High"
3. User enters a guess of 25, and the game shows "Too High"
4. Score updates correctly after each guess
5. Game ends after the correct guess 

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

```
# Paste your pytest output here, e.g.:
# pytest tests/
# ========================= X passed in 0.XXs =========================

(.venv) nadia@new-host-8 glitch-game % python3 -m pytest                                
================================== test session starts ===================================
platform darwin -- Python 3.13.16, pytest-9.1.1, pluggy-1.6.0
rootdir: /Users/nadia/CodePath/glitch-game
plugins: anyio-4.15.1
collected 6 items                                                                        
tests/test_game_logic.py ......                                                    [100%]

=================================== 6 passed in 0.06s ====================================
```

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
