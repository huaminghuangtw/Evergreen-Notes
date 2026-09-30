---
title: Prompt Engineering
modified: 2026-09-30
---

# When You’re Writing the Prompt

> Source: [Prompting Best Practices - Claude](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices)

1. **Set the frame first.** Give a **role** in the system prompt, patterned as _expert + task_: “You are a helpful coding assistant specializing in Python.” Be explicit about format and constraints, and use numbered steps when order or completeness matters.
2. **Be imperative, clear, and concrete.** Ask for the change, not for suggestions; say what _to do_, not what to avoid.
	 * **Less effective:** “Can you suggest some changes to improve this function?”
	 * **More effective:** “Change this function to improve its performance.”
3. **Explain why.** The model generalizes from the _reason_, not just the _rule_.
	 * **Less effective:** “NEVER use ellipses.”
	 * **More effective:** “Your response will be read aloud by a text-to-speech engine, so never use ellipses, since the engine won’t know how to pronounce them.”
4. ⭐️ **Structure the input.** Tag each content type with XML — `<instructions>`, `<context>`, `<input>`, `<examples>` — so instructions don’t blur into data, and show 3–5 relevant, diverse examples for anything with a repeated format.
	* Tag the **long or ambiguous** part and leave short details inline: wrap the pasted code in `<code>…</code>`, but mention the language as a plain sentence — “The code is written in Python.”
5. **Long input first, question last.** Put documents above the query, and have it quote the relevant passages into `<quotes>` before answering.
6. ⭐️ **Ask it to reason, then to check itself.** “Think thoroughly” beats a hand-written step-by-step plan, and a self-check against explicit criteria catches errors in coding and math.
	 * Give it somewhere to think ([chain of thought](https://docs.anthropic.com/en/docs/let-claude-think)): “In a `<scratchpad>`, brainstorm 3 options and give a brief rationale for each.”
7. **Match the prompt’s style to the output you want.** Markdown-heavy prompts breed markdown-heavy answers; for long-form writing, ask for flowing prose and reserve lists for genuinely discrete items.
8. **Dial the aggression down.** “CRITICAL: you MUST…” now over-triggers on current models — plain “Use this tool when…” is enough.
9. **Ask for above and beyond explicitly.** Current models follow instructions literally instead of inferring ambition.
	 * **Less effective:** “Create an analytics dashboard.”
	 * **More effective:** “Create an analytics dashboard. Include as many relevant features and interactions as possible. Go beyond the basics to create a fully-featured implementation.”
10. **Ask for clarifying questions.** End every prompt with “before answering, ask as many clarifying questions as needed” — it forces hidden assumptions into the open before the model commits to an answer.
11. **Define every term that matters.** Spell out each important term so nothing is assumed or vague.
12. **Constrain scope and set the brakes.** Only the requested or clearly necessary changes; confirm before anything destructive, hard to reverse, or visible to others.

---

# When One Shot Isn’t Enough

> Source: [ChatGPT Prompt Engineering for Developers - DeepLearning.AI](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/) by Andrew Ng

1. **Start general, then get specific.** Open broad, then add constraints in follow-ups:
	 * “Generate a Calculator class.”
	 * “Add methods for addition, subtraction, multiplication, division, and factorial.”
	 * “Don’t use any external libraries and don’t use recursion.”
2. **Break the task down.** Instead of “build a meal planner app,” ask for one function at a time: ingredients → recipes, recipes → shopping list, recipes → weekly meal plan.
3. **Iterate instead of rewriting.** Refine with follow-up prompts:
	 * “Write a function to calculate the factorial of a number.”
	 * “Don’t use recursion and optimize by using caching.”
	 * “Use meaningful variable names.”

---

The best way to create prompts is to ask the AI agent to create them for you.

---

[Getting Started with AI: Good Enough Prompting](https://huam.ing/getting-started-with-ai-good-enough-prompting)
