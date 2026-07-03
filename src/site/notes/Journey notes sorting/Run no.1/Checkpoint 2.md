---
{"dg-publish":true,"permalink":"/journey-notes-sorting/run-no-1/checkpoint-2/"}
---

##### Let's get it started!
### ‎June ‎25, ‎2026
+ Full memory pipeline: `mem_manager.` → `stm` → `ltm` → `session_vault` → `filter` → `cross_vault`

- Built based on the function of a USB hub: 
	- `mem_manager`: Essentially the "USB hub" that plugs into the "computer" which is the main AI pipeline, `main`. It relies on the `cls` function of the composing `.py` files as the "connectors"
		
	- `stm`: Introduces `STM` class. An upgrade from the previously basic STM, mentioned in [[Journey notes sorting/Run no.1/Checkpoint 1\|Checkpoint 1]]. It now includes `time` and a more advanced memory decay system to pave way for future upgrades and advancements; all the while still keeping the relatively compact and simple nature - as it should.
		
	- `ltm`: Introduces `ActiveLTM` class, which collects from `stm` and utilizes an LLM called via API key method to extract meaningful and excess-free patterns/memories from the conversation; which are then appended to `i-s_long_term.json`
		
	- `session_vault`: Introduces `SessionVault` class. It collects the memories fallen out of relevance, and summarizes them in form of "topics" to be recalled later. I once thought this obsolete, but realized just a little while later that `ltm` is *oblivious* to topic shifts. And so, `session_vault` is created to intelligently combat the cross-topic problem alongside `filter` and `cross_vault` like the Holy Trinity except they caused me headaches.
		
	- `filter`: Introduces `ShiftFilter` class. It calls an LLM via API key method, with strict token and temperature tweaks, to determine whether the main intent, aka topic, of the current few exchanges has changed.
		
	- `cross_vault`: Introduces `CrossVault` class. Currently, it sits as a fleshed out system for a module that extracts memories that persists across sessions/program restarts; but not yet meaningfully integrated into `main`. Nonetheless, this will go big later once I figure out how to fetch and store memories with this.

--- 
### June 30, 2026

- Figured out a system to integrate and store memories in `cross_vault`.
	- Introduce `TopicChecker` class to `filter`. It will be triggered by `ShiftFilter`, which lays inside the same script, to check if the new memory is actually "new", or a duplicate of an already-existing memory inside `cross_vault`. As I write this, I also realized its potential for being a solution to a myriad of context-based problems that might pop up in later stages of testing and use.
	- As for `cross_vault`, It will function as such:
		- When triggered by `TopicChecker`, it will recall OR update an already-existing memory inside the storage as per the conditions mentioned above.
		- Will automatically run when shutting down, pulling all of the entries in `session_vault` to compress and stored into a global file that persist across sessions. This keeps things compact, concise, and manageable; and fits my current hardware.

---
### Conclusion
This is the pivotal moment in this project, as you can probably tell from the mountain of changes.
However, one must remember that this is just my past vision fully realized; meaning, if I hadn't taken my time back then, I wouldn't know anything now.
In short, I am grateful for my will to start and my persistence - or stubbornness.