# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").

--- One, the hints were backwards. Two, the easy difficulty gives us a range of 20, normal has 100 yet hard has 50, which should not be the case. Three, when looking at the Developer Debug Info tab, the previous game's history of guess show up even when starting a new game. Four, I finished a game and was able to switch difficulty from normal to hard and my attempts showed "-3", also shouldn't be there and shouldn't be able to guess until New Game is selected. Five, whenever I want to start a New Game it won't let me unless I reload the site. Six, New Game history isn't clearing the previous game's history.

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
I used Copilot and Claude for this project as both are installed in my VS Code and gives me two options as opposed to just using one tool.
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
AI suggested that from lines 37-47 in the app.py code is where I was experiencing that when we are playing guess the number and my guess is lower than the secret number, it told me to go higher and to guess higher when my guess is higher than the secret number. I was given a simple solution to just switch the words in the if statement return strings and helps those playing to make better guesses.
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
Here is something that the AI suggested me to change and was incorrect: 'line 87, so switching difficulty in the sidebar will now correctly update both the displayed range and the generated secret number.' This suggestion when used from the AI ended up not working and so had to find another solution.
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
I decided this by running a few tests before looking to find the next bug. 
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
  I ran the pytest and it said that I passed all the tests. The test_winning_guess, test_guess_too_high, test_guess_too_low, and test_hint_message_direction. 
  I ran a test manually after fixing the bug that wouldn't allow me to start a new game. Now the New Game works and runs just as the first game works. No need to reload the website now. 
- Did AI help you design or understand any tests? How?
Claude helped me understand how to get the pytest running. It is needed to be running on our own virtual environment in order to do so. All my tests passed after an empty conftest.py was made by Claude Code. What is interesting is that it passed all tests on my third attempt of pytest. 
---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
The code for the secret number was not put in a condition statement. That made it as if we needed to keep finding a new secret number every time and would make a bad user experience.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
Streamlit "reruns" would be the same as if I am writing text in a search bar on any website and then reloading that website without pressing search. This means that whatever we wrote on that search bar has been cleared as we would be starting off on that website from the beginning. Thus, having to again write something on that search bar until I want to do another action.
- What change did you make that finally gave the game a stable secret number?
The if statement made on lines 32-33 in app.py allowed the game to keep a stable secret number. Without the conditional, the following: "st.session_state.secret = random.randint(low, high)", would simply have kept our game changing the secret number after each guess making it unfair to the user.

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
  One habit that I will reuse is to not be scared to ask the wrong questions as that would prohibit me from learning from the AI.
- What is one thing you would do differently next time you work with AI on a coding task?
One thing I would do differently is my approach. I'm not new to using AI but I am new to creating agents which allow us to focus on specific tasks we want the AI to do whilst working/testing other features of whatever the project may be.
- In one or two sentences, describe how this project changed the way you think about AI generated code.
I can also add for you here that I did agree with most of what AI has generated for me in terms of its code. Although, I do see why there needs to be self debugging going forward in other projects.