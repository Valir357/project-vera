---
{"dg-publish":true,"permalink":"/journey-notes-sorting/code/checkpoint-5/","dg-note-properties":{}}
---

### July 15, 2026
I finally got my hands on a searching tool, which I can implement into Vera.
🔹Vera can now search the web for missing information
	🔸But for now, she can only look for what is available on Wikipedia
	🔸The query system is still flawed, oftenly hitting a brick wall solely due to bad queries

My goal is to move beyond this, giving Vera the ability to search whatever, whenever, and wherever is needed.

---
### July 21, 2026
No progress in codes, but I am learning about the search function that major AIs use; safe to say, it proves more challenging than it originally appeared, and far more complex than what I built above.

However, from my current understanding, its structure is... *not* unlike what I have built, or at least thought of in the past, namely:
- 🔸Trigger system
- 🔸Result candidates system
- 🔸Result confidence/scoring system (or result filtering system in general)

All of which were briefly touched upon or even heavily considered [[Journey notes sorting/Code/Checkpoint 3\|when designing the filter system for my c-s_vault]]
Anyhow, this is a stage slower and more methodical than others before it, and should be taken with according pace.

---
### July 27, 2026
Finally got somewhere, I am ecstatic.
After overthinking for two days or so, I decided to go back to the roots and answer *humanly* questions: ***"When should I look a thing up?"*** And ***"Why should I look that thing up?"***
Then I follow them up with creating queries, extracting results, and somehow turning the extracted info into something usable for the main prompt (current big question btw).

But for now, I made the barebones. It contains only data structures, no complex behavior yet—later search components will exchange those.
When broken down, its simplicity shows:
```
Why search? Are you positive?
    ↓
Let's look it up
    ↓
Initial results; think skimming the page first
    ↓
Turning the initial results into something the system can work with
    ↓
Double check; does it really answer the question, or just a dud?
    ↓
Final result; fed to the main loop
```
