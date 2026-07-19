---
title: How to use AI effectively
modified: 2026-07-19
---

> The dumbest person you know is currently being told “You’re absolutely right!” by ChatGPT.

---

**AI 是想法的「放大器/加速器」，而不是想法的「產生器」。**[^1]

The intended roles AI should play: Treat it as a collaborative partner—an _assistant_, _co-worker_, _helper_, _coach_, or _adviser_—not a _contractor_ to whom you completely delegate your tasks and offload your responsibilities. <mark>Remember: What you outsource will _atrophy_.</mark>

AI is an eager intern or new grad hire, not a senior engineer. Give it the work nobody else wants, check every output, and never hand mission-critical work to it.

Analogy:

* 「0 到 1」的突破仰賴人類的創造力，而 AI 工具則擅長將「1 到 100」的流程高效擴展。
* 備料 → 煮飯 — 人類準備原料（想法、脈絡），AI 負責烹調上菜
* 點 → 線 + 面 — 人類提供零散點子，AI 將其串聯成有結構的成果

---

# [The Bicycle of the Mind](https://chengweihu.com/six-tiny-musings-on-ai/)

AI is not just a tool, but an extension of our will, allowing us to accomplish feats that were once thought impossible.

> [“We humans are tool builders. [...] And so for me, a computer has always been a bicycle of the mind. Something that takes us far beyond our inherent abilities.” — Steve Jobs](https://allaboutstevejobs.com/videos/misc/future_of_pc_1990)

人類的價值：定義問題＋用全域視野調度 AI 工具

---

* **I think before I prompt.** I clarify the problem, my perspective, and what I actually believe before asking a machine to weigh in.
* **I write before I refine.** I force myself to produce a bad first draft before touching any tools.
* **I decide before I optimize.** I form an initial core judgement by myself, then use tools to pressure-test or improve it.

---

Prompt Engineering (提示詞工程) ➞ Context Engineering (脈絡工程) ➞ Harness Engineering (駕馭工程)

---

**[Remember to be kind to AI.](https://www.reddit.com/r/singularity/comments/xi51fn/remember_to_be_nice/)** Saying “please” can actually improve accuracy by signaling to the model that you’re issuing a command rather than asking a question, which helps narrow the search space.

---

# A/B Testing

Develop an _[experimental mindset](the-growth-mindset.md)_ when using AI—treating it as a partner to learn from through trial and error.

---

Basic Invitation Structure: _“Act as a \[ROLE\] perform \[TASK\] in \[FORMAT\]”_

---

The best way to create prompts is to ask the AI agent to create them for you.

---

# [ChatGPT Prompt Engineering for Developers - DeepLearning.AI](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/) by Andrew Ng

* Start general, then get specific.

	```text
    Generate a Calculator class.
    Add methods for addition, subtraction, multiplication, division, and factorial.
    Don’t use any external libraries and don’t use recursion.
    ```

* Break down complex tasks into simpler tasks. For example, instead of asking AI to generate a meal planner app, break it down into smaller tasks:
	* Generate a function that takes a list of ingredients and returns a list of recipes.
	* Generate a function that takes a list of recipes and returns a shopping list.
	* Generate a function that takes a list of recipes and returns a meal plan for the week.
* Iterate on your prompts. Provide follow-up prompts to refine or modify the response. For example:
	* “Write a function to calculate the factorial of a number.”
	* “Don’t use recursion and optimize by using caching.”
	* “Use meaningful variable names.”
* Give examples of what you want.

	```text
    Generate a function that takes a string and returns the number of vowels in it.
    Example:
    findVowels("hello") returns 2
    findVowels("sky") returns 0
    ```

---

# For software development

AI tools are a force multiplier. **Not for code generation** [^2], but for the hardest part of software development: learning new things, and _applying them appropriately_. **Don’t use it solely to gather information.** Treat it as a personalized learning companion/tutorial to explore ideas and deepen your understanding of key concepts. [^3] Be sure to [take notes](note-taking.md) along the way.

---

**Never consume “LLM copy-pasta” without scrutiny.** [^4] Always validate the information and think critically using your own understanding.

> In my opinion, the biggest issue is the complete lack of problem-solving and debugging skills. The second is an over-reliance—you can’t do anything without it guiding you step by step.

---

A good LLM serves as a great groove-greaser / a productivity catalyst—helping you dive into focused work (e.g., boilerplates) or more informed research faster. It’s invaluable for <mark>filling in the gaps</mark>. [^5] For example, onboarding faster into unfamiliar codebases—ask AI to explain, summarize, or navigate the code.

---

[AI tools are ironically way more useful for experienced devs than novices.](https://www.reddit.com/r/ExperiencedDevs/comments/1jzpzkm/ai_tools_are_ironically_way_more_useful_for)

* Bad programmer + AI = Lots of bad code
* Medium programmer + AI = Lots of medium code
* Great programmer + AI = Lots of great code

> Low-skill developers can produce bad code much faster, while high-skill developers can produce good code even faster.

---

## [Best practices for using AI in VS Code](https://code.visualstudio.com/docs/copilot/copilot-tips-and-tricks)

* Write natural language comments before coding:

	```python
	# Function to fetch user data from an API and return JSON response
	```

	* Helps in generating **more relevant** code
	* Works well for boilerplate and repetitive tasks
* Use Copilot **as an assistant, not a replacement** :
	* Still apply **your own coding knowledge**
	* Use Copilot to explore **alternative solutions**
	* Never **blindly accept** Copilot’s suggestions—review for:
		* **Correctness** (logic, syntax, and expected output)
		* **Security risks** (avoiding hardcoded secrets or unsafe patterns)
		* **Performance considerations**
* Keep chat history relevant. Provide the right context.
	* Reference files, folders, or symbols in your prompt by using `#<file name>`, `#<folder name>`, or `#<symbol>`.
	* Drag and drop files, folders, or editor tabs onto the chat prompt.
	* Add problems, test failures, or terminal output to your prompt.
	* Add images or screenshots to your prompt.

---

[AI Prompt Hacks](ai-prompt-hacks.md)

---

[Getting Started with AI: Good Enough Prompting](https://huam.ing/getting-started-with-ai-good-enough-prompting)

[^1]: 修潤，而非生成。
[^2]: Why? They often hallucinate confidently.（一本正經地胡說八道/講幹話、似是而非、包裝得煞有其事）
[^3]: Surface knowledge is easy. Real knowledge still has to be earned.
[^4]: Even when you copy code from elsewhere, you should always type it out manually. Why? It helps reinforce the syntax and structure in your mind. By physically typing the code, you engage more actively with it, which can lead to better understanding and retention.
[^5]: Most of a software engineer’s work doesn’t involve writing everything from scratch, but rather adapting new requirements into layers of code shaped by generations of other engineers. In these situations, what’s truly needed is **[patience](a-man-who-is-a-master-of-patience-is-master-of-everything-else.md)**—and a deep understanding of how others have built and thought through the system.
