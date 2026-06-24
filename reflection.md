# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
The game has a prompt to guess a number between 1 and 100 with 7 attempts. After entering my guess, it gave a hint to go lower. However, after entering several guesses, the hint never chanced even when putting 1. 
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").
The first hint was backwards because the secret was 65 while my first guess was 5 and it said go lower. Even when I put 100, the guess still said guess lower, so the hint seems to not change. When I put 1, the hint still said go lower. 
**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
| 50    |       Go Higher!  |    Go Lower!    |      none              |
| 25    |       Go Lower!   |    Go Higher!   |      none              |
| 75    |       Go Higher!  |    Go Lower!    |      none              |

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
Claude
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
I told it the hint given is opposite to the answer. The AI suggested that the message was worded wrong because it had "Go Lower!" associated with the guess being too low and same for too high. Too verify, I rewrote that section and guessed to see if the hints matched. 
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
The AI suggested that the resetting secret number might be from a missing return statement. However, I realized it was because the random.randint() was being called outside of st.session_state. Therefore, Streamlit was creating a new secret number every time. 
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
I decided the bug was fixed when I was able to match the Developer Debug Info consistently. 
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
For the bug with the opposite hints, I made sure to guess a number lower than the secret number and see if it would show "Go Higher!". 
- Did AI help you design or understand any tests? How?
The AI helped me understand that testing the logic separately from Streamlit is also important because pytest couldn't work with the web app. 
---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
Streamlit reruns the entire script every time a user interacts with something. Therefore, variables can reset every time the app reruns. To stop this, session states can be used to store data so that variable does not get reset. 
---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
One habit I want to continue using is testing my code more often because it makes it easier to backtrack if I ever am not sure if I need to go back and change my old changes. 
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
Next time, I can be more specific and add more context to my prompts when working with AI. This can help the AI give more accurate suggestions. 
- In one or two sentences, describe how this project changed the way you think about AI generated code.
This project showed me that AI is very helpful in explaining code, but I need to be more proactive to maximize my use of AI to help me. 
