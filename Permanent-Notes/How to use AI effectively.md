---
title: How to use AI effectively
created: 2024-11-18T10:16:50
modified: 2025-08-01T19:43:14
---

**[Getting Started with AI: Good Enough Prompting | One Useful Thing](https://www.oneusefulthing.org/p/getting-started-with-ai-good-enough)**

> As a [New York Times article on the paper](https://www.nytimes.com/2024/11/17/health/chatgpt-ai-doctors-diagnosis.html) reported: “they were treating \[the AI\] like a search engine for directed questions: 'Is cirrhosis a risk factor for cancer? What are possible diagnoses for eye pain?' It was only a fraction of the doctors who realized they could literally copy-paste in the entire case history into the chatbot and just ask it to give a comprehensive answer to the entire question.” […] There are many stumbling blocks: people treat AI like Google, asking it factual questions. But AI is not Google, and do not provide consistent, or even reliable, answers.

* AI's potential is wasted without the right approach.
	* Doctors using GPT-4 for diagnoses performed no better than those without it—and both did worse than GPT-4 alone. Why? They treated the AI like a search engine, asking narrow, factual questions instead of giving it full context and leveraging its ability to synthesize complex information.

> AIs are inconsistent and weird, and often have different results across different models. For example, they [are sensitive to small changes in spacing or formatting](https://arxiv.org/abs/2310.11324); they get [more accurate when you tell them to “read the question again;”](https://arxiv.org/pdf/2309.06275) they [seem to respond better to politeness (but don’t overdo it](https://arxiv.org/abs/2402.14531)); and they [may get lazier in December, perhaps because they have picked up on the concept of winter break](https://x.com/emollick/status/1734280779537035478). Add to all of this the fact that getting good results out of AI without a lot of formal training is likely growing easier as [larger models are less sensitive to changes in prompting technique than older AIs](https://arxiv.org/abs/2410.12405), and new techniques allow the AI to [improve your prompt for you](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/prompt-generator).

> You can learn details of prompt engineering and [the basics of how LLMs work](https://www.oneusefulthing.org/p/thinking-like-an-ai), of course, but for most people, that is not a required starting place. You just need to use AI enough to get a feel for what you can use it for in your area of expertise. **The most important thing to do is to get 10 or so hours of use with an advanced AI system.** And to do that you just need to be a good-enough prompter to overcome the barriers that hold many AI users back.

> The single most useful thing you can do to understand AI is to use AI. There are lots of reasons people may decide to give up on using an AI quickly, from early hallucinations (the AI isn't good enough) to existential discomfort (the AI is _too_ good), but many of those initial reactions are tempered over time. Your goal is simple: spend 10 hours using AI on tasks that actually matter to you. After that, you'll have a natural sense of how AI fits into your work and life. You'll develop an intuition for effective prompting, and you'll better understand AI's potential.

* Prompt engineering isn't the place to start.
	* Instead, the key is spending 10 hours using AI on tasks you care about. This hands-on experience helps you naturally develop the intuition needed to prompt effectively.

> I mean literally _**treat AI just like an infinitely patient new coworker who forgets everything you tell them each new conversation.**_ Two parts of this are analogous to working with humans (being new on the job and being a coworker) and two of them are very alien (forgetting everything and being infinitely patient). We should start with where AIs are closest to humans, because that is the key to good-enough prompting. As it is a coworker, **you want to work with it, not just give it orders**, and you also want to learn out what it is good or bad at.

> **Start by using it in areas of your expertise**, where you are able to quickly figure out the shape of the [jagged frontier of its ability](https://www.oneusefulthing.org/p/centaurs-and-cyborgs-on-the-jaggedh). Because you are expert, you will be able to quickly assess where the AI is wrong or right. You do need to be prepared for it to give you plausible but wrong answers, but don't let the risk of these hallucinations scare you off initially. Though hallucinations may be inevitable, you will learn where they are a big deal, and where they are not, over time. You can reduce the rate of hallucinations somewhat by [giving the AI the ability to be wrong,](https://docs.anthropic.com/en/docs/test-and-evaluate/strengthen-guardrails/reduce-hallucinations#example-analyzing-a-merger-and-acquisition-report) for example, writing: _if you're unsure or necessary information, say “I don't have enough information to answer this”_ can make a big difference.

* Instead of treating AI as an intern or new grad hire, treat it like an infinitely patient coworker who:
	* Is highly capable but needs specific guidance.

		> Since the AI is new on the job, so you need to **be very clear \[and detailed\] on exactly what you want \[in the prompts\]**. You don't want _a report on the pros and cons in remote learning_, you want _a report on the pros and cons in remote learning appropriate for a regional university in the Midwestern US and that might convince a business school Dean to fund a new remote learning program._

		> Other ways to help give the AI clarity is by **giving the AI examples of good or bad responses** (called “Fewshot Prompting”) and **giving it step-by-step directions** of what you want to accomplish.

		> You can also give it feedback just as you would another human being asking for improvement or just request that it ask you questions about anything that is unclear.

	* Forgets everything at the end of each conversation.

		> Now let's talk about the less human aspects of AI, like its forgetfulness - the fact that each new conversation wipes the AI's understanding of your particular situation. As a result, you also need to **provide context.**

		> Try roles out, but you don't need to use them if they are not useful. **You can also just give it whatever information you have lying around. Entire documents, instruction manuals, or even previous conversations are often helpful**, [just remember to pay attention to the AI’s memory, its context window.](https://www.oneusefulthing.org/p/thinking-like-an-ai)

	* Never gets annoyed and tired of iterating.

		> This introduces something new in intellectual life, **abundance**. You don't need to ask for one email, ask for three in different tones to inspire you. You don't need to ask for one way to complete a sentence, ask for 15 options and see if that unlocks your writing. Don't ask for 5 ideas, ask for 30.

		> Your job becomes one of pushing for variation (“give me ideas that are 80% weirder”), recombination (“combine ideas 12 and 16”) and expansion (“more ideas like number 12”), before selecting one you like.

> **Working with AI is a dialogue, not an order.**

> For getting a thinking partner, the key to using the AI is to have a **natural dialogue**. Just talk to it. Most people find this easiest to do **via voice on their phone**.

---

**[Remember to be kind to AI.](https://www.reddit.com/r/singularity/comments/xi51fn/remember_to_be_nice/)** Saying “please” can actually improve accuracy by signaling to the model that you're issuing a command rather than asking a question, which helps narrow the search space.

---

Develop an _experimental mindset_ when using AI—treating it as a partner to learn from through trial and error. → **A/B Testing**

----

[ChatGPT Prompt Engineering for Developers - DeepLearning.AI](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/) by Andrew Ng

* Start general, then get specific.

	```
    Generate a Calculator class.
    Add methods for addition, subtraction, multiplication, division, and factorial.
    Don't use any external libraries and don't use recursion.
    ```

* Break down complex tasks into simpler tasks. For example, instead of asking AI to generate a meal planner app, break it down into smaller tasks:
	* Generate a function that takes a list of ingredients and returns a list of recipes.
	* Generate a function that takes a list of recipes and returns a shopping list.
	* Generate a function that takes a list of recipes and returns a meal plan for the week.
* Iterate on your prompts. Provide follow-up prompts to refine or modify the response. For example:
	* “Write a function to calculate the factorial of a number.”
	* “Don't use recursion and optimize by using caching.”
	* “Use meaningful variable names.”
* Give examples of what you want.

	```
    Generate a function that takes a string and returns the number of vowels in it.
    Example:
    findVowels("hello") returns 2
    findVowels("sky") returns 0
    ```

---

Basic Invitation Structure: _“Act as a \[ROLE\] perform \[TASK\] in \[FORMAT\]”_

---

# Tasks

* Pushing you to think through your own ideas
	* Use AI as a rubber duck
	* Critic: _“Critique my argument: \[argument\]”_
* Writing a cover letter
	* “Write me a personalized cover letter explaining why I'm a great candidate for this job. The job title is [Job Title], the company is [Company Name], and here is the job description: [Paste Job Description]”
	* “Revise and personalize this cover letter using my resume: [Paste Resume Content]”
* ⭐️ Improving prompts

---

“**[The Bicycle of the Mind](https://chengweihu.com/six-tiny-musings-on-ai/)**” — AI is not just a tool, but an extension of our will, allowing us to accomplish feats that were once thought impossible.

> _[“We humans are tool builders. [...] And so for me, a computer has always been a bicycle of the mind. Something that takes us far beyond our inherent abilities.” — Steve Jobs](https://allaboutstevejobs.com/videos/misc/future_of_pc_1990)_

---

# [Github Copilot](https://code.visualstudio.com/docs/copilot/overview)

* Keyboard Shortcuts
	* Toggle Copilot Chat: <kbd>Ctrl</kbd> + <kbd>Cmd</kbd> + <kbd>I</kbd>
	* Toggle Editor Inline Chat: <kbd>Cmd</kbd> + <kbd>I</kbd> (if you're focused in the code editor)
	* Start Voice Chat: <kbd>Cmd</kbd> + <kbd>I</kbd> (if you're focused in the Copilot Chat view)
	* Create New Chat
		* <kbd>Cmd</kbd> + <kbd>N</kbd>
		* <kbd>Ctrl</kbd> + <kbd>L</kbd>
	* Manage Models: <kbd>Cmd</kbd> + <kbd>Opt</kbd> + <kbd>.</kbd>
	* [Run prompt (or create a new prompt file)](https://code.visualstudio.com/docs/copilot/copilot-customization#_use-a-prompt-file-in-chat): <kbd>Ctrl</kbd> + <kbd>Opt</kbd> + <kbd>/</kbd>
	* Commands
		* Type `#` to add context (e.g., `#file`, `#folder`, etc.)
		* Type `/` to use commands (e.g, `/explain`, `/fix`, `doc`, `/tests`, `/help`, etc.)
* Use Cases
	* Onboard faster into unfamiliar codebases—ask Copilot to explain, summarize, or navigate the code.
* [Best Practices](https://code.visualstudio.com/docs/copilot/copilot-tips-and-tricks)
	* Guide Copilot by writing natural language comments before coding:

		```python
		# Function to fetch user data from an API and return JSON response
		```

		* Helps in generating **more relevant** code
		* Works well for boilerplate and repetitive tasks
	* Use Copilot **as an assistant, not a replacement** :[^1] [^2]
		* Still apply **your own coding knowledge**
		* Use Copilot to explore **alternative solutions**
		* Never **blindly accept** Copilot's suggestions—review for:
			* **Correctness** (logic, syntax, and expected output)
			* **Security risks** (avoiding hardcoded secrets or unsafe patterns)
			* **Performance considerations**
	* Keep chat history relevant. Provide the right context.
		* Use `#codebase` to refer to the entire codebase.
		* Use the `#fetch` tool to fetch content from a web page or use `#githubRepo` to perform a code search on a GitHub repository.
		* Reference files, folders, or symbols in your prompt by using `#<file name>`, `#<folder name>`, or `#<symbol>`.
		* Drag and drop files, folders, or editor tabs onto the chat prompt.
		* Add problems, test failures, or terminal output to your chat prompt for scenario-specific context.
		* Add images or screenshots to your prompt to let Copilot analyze the image.
	* [Reuse prompts with prompt files](https://code.visualstudio.com/docs/copilot/copilot-customization#_prompt-files-experimental)
	* [Personalize/Customize Copilot with instruction files](https://code.visualstudio.com/docs/copilot/copilot-customization#_custom-instructions)

[^1]: The intended roles AI should play: Treat it as a collaborative partner—an _assistant_, _co-worker_, _helper_, _coach_, or _adviser_—not a _contractor_ to whom you completely delegate your tasks and offload your responsibilities. ==It's important to remember: What you outsource will _atrophy_.== →「0 到 1」的突破仰賴人類的創造力，而 AI 工具則擅長將「1 到 100」的流程高效擴展。→「修潤，而非生成。」
[^2]: The proper use of AI tools is to treat them like an intern or new grad hire. You can give them the work that none of the mid-tier or senior people want to do, thereby speeding up the team. But you will have to review their work thoroughly because there is a good chance they have no idea what they are actually doing. If you give them mission-critical work that demands accuracy or just let them have free rein without keeping an eye on them, it's likely you are going to regret it.
