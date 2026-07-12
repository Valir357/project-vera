---
{"dg-publish":true,"permalink":"/journey-notes-sorting/code/checkpoint-4/","dg-note-properties":{}}
---

### July 10, 2026
This day, Vera gained her (intended) voice
- 🔹Switched from `edgetts` to `COEIROINK`, a Japanese voice synthesizer.
	
- 🔹Replaced `mistral-3b-2512`model with `qwen-2.5-7b-instruct`for more compatibility with Japanese language
	- 🔸Also added an auto translator using `self.llm( )`for testing; at least, while I still don't know Japanese.

The original goal is for Vera to come to the Japanese people (read about [[Main/Vera\|Vera]]), so this is a considerably big step.
Of course, I keep a backup for the `edgetts` version around in case something breaks, as is the previous Checkpoints.

--- 
### July 12, 2026
- 🔹Successfully (re)deployed Vera to the Discord platform in form of a chatbot registered through Discord Developer Website.
	- 🔸Instead of replying to the terminal then speak the response, she now only texts to the Discord room.

The next stage is to (re)deploy her to the Twitch platform, which forces myself to ask the golden question: `"If she makes it to the big screen, how will she interact with me and the audience?"`
But for now... peace ✌