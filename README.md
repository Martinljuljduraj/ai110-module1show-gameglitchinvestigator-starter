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
Issue fixed
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
Issue fixed
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!
   All my tests passed after an empty conftest.py was made by Claude Code. What is interesting is that it passed all tests on my third attempt of pytest. 

## 📝 Document Your Experience

- [ ] Describe the game's purpose.
A number guessing game where the player tries to guess a randomly generated secret number within a limited number of attempts. 
- [ ] Detail which bugs you found.
I written the following in the reflection.md file and will post that answer here as those are all the bugs that I found: One, the hints were backwards. Two, the easy difficulty gives us a range of 20, normal has 100 yet hard has 50, which should not be the case. Three, when looking at the Developer Debug Info tab, the previous game's history of guess show up even when starting a new game. Four, I finished a game and was able to switch difficulty from normal to hard and my attempts showed "-3", also shouldn't be there and shouldn't be able to guess until New Game is selected. Five, whenever I want to start a New Game it won't let me unless I reload the site. Six, New Game history isn't clearing the previous game's history.
- [ ] Explain what fixes you applied.
Fixed the difficulty range, hint messages were swapped, the New Game button previously didn't work, History now clears when clicking New Game, logic has been refactored into logic_utils.py, and finally tests were fixed and have passed.

## 📸 Demo

- [ ] [Insert a screenshot of your fixed, winning game here]
![alt text](<Fixed Winning Game.jpg>)

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, insert a screenshot of your Enhanced Game UI here]
