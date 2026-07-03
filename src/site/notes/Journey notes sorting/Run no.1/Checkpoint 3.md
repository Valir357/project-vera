---
{"dg-publish":true,"permalink":"/journey-notes-sorting/run-no-1/checkpoint-3/"}
---

### July 3, 2026

This day, I flesh out the planned system.
- `class TopicChecker`: Uses a multi-layer scoring system to determine whether or not the new topic detected by `class ShiftFilter` is truly "new", or just referencing something already existed inside `cross_vault`.
	- The first layer uses a crude scoring system to get a list of "candidates" to then be passed into the LLM layer.
	- The LLM layer (`self.llm()`) acts as the final judge of the "candidates" sent by the previous layer.
		- + If the "candidate" passes both layers, they will be recalled from `cross_vault`
		- - If the "candidate" fails both layers, or fails at either one, they will be appended as a new memory inside `session_vault`, waiting to be added to `cross_vault` later.
	
- This design is made so that neither layer is the sole crutch of this memory fetching system, effectively boosting accuracy and consistency through a unified scoring system.
- Speaking of the scoring system, it has also been added to `ltm` and `session_vault` to significantly reduce the bloats and non-essential memories/patterns about its chatter.

---
### Conclusion
This is the foundation, the base, in all its glory!
1,060 lines of code. Rigorously tested, refined, and even reforged in the middle - when I thought I lost sight of where I was.
From here, I can rebuild the many bots and AI programs I had planned before but not organized enough to even know where to start.