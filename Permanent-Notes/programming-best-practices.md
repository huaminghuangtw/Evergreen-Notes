---
title: Programming Best Practices
modified: 2026-05-07
---

# Code should be self-commenting

Comments are for _why_, not _what_.

Avoid obvious or redundant comments that simply restate what the code does:

```text
int i = 2; // set i to 2   ← (❌ This adds no value)
```

Instead, use comments to explain the reasoning, intent, or context behind your code—_why_ you are doing something (how it fits into the bigger picture):

```text
int i = 2; // Start from index 2 to skip the first two elements, which have already been processed in the previous step.
```

---

Use descriptive and human-readable names for variables. Name methods as verbNoun like `calculateSum` or `findElement`.

Also, be precise with singular and plural names. For example, use `getCustomer` for a function that returns a single customer, and `getCustomers` for one that returns a list. Mismatched naming leads to confusion and bugs.

---

養成在 Code 裡面 Tag `#TODO`, `#FIXME`, `#BUG`, `#NOTE`, `#OPTIMIZE` 的習慣

---

Always consult official documentation first. Never use tutorials or videos as your main reference. Third-party content can be outdated, incomplete, or even incorrect.

---

Setup automatic linters and formatters.

---

Write clean, compact, clear, readable, modular, and [extensible](https://en.wikipedia.org/wiki/Extensibility "Extensibility") code that can be easily maintained and repurposed by developers other than its creators.

> The ratio of time spent reading versus writing is well over 10 to 1. We are constantly reading old code as part of the effort to write new code. \[…\] Therefore, making it easy to read makes it easier to write.

* Be aware of the “Technical Debt.”
* Good code is code that can be understood by a junior engineer. Great code can be understood by a first year CS freshman. The best code is no code at all.
* Review your own code.
* Pro Tip: Review your own code - Make a habit of opening a pull request (PR) for your own changes instead of taking the easy route and just pushing to master—even if you’re working solo. Imagine yourself from the perspective of someone else trying to read your code without all the context.

---

# Don’t over-engineer

> “Premature optimization is the root of all evil.” — Donald Knuth

* The hallmark of premature optimization is adding complexity for the sake of efficiency, _without_ having determined that the benefit is substantial enough to justify the cost (of both implementation and maintenance).
* Get things work first. Test the smallest (reusable) unit/module first (like LEGO blocks).
* Stick to the requirements of _today_, without trying to solve complex problems of _tomorrow_.
* Solve only the problems that you have today!
* “Shipping _high quality software_ within a _reasonable time frame_ is of utmost priority.”
* “Lot of the times, engineers tend to solve problems that don’t exist today.”

---

# Focus on High-level OO Design Patterns & SOLID Principles

> Fundamentals > Frameworks

* Single Responsibility Principle (SRP)
	* A class should only have one reason to change.
	* A module should be responsible to one, and only one, actor.
* Separation of Concerns (SoC) → Dependency Management
	* Modular Code
	* You should break things up.
	* Separate an application into self-contained units, with minimal overlapping between the functions of the individual units.
	* Modularity/Granularity is achieved by [encapsulating](https://en.wikipedia.org/wiki/Encapsulation_(computer_science)) information inside a section of code that has a well-defined client/user **interface**. Encapsulation is a means of [information hiding](https://en.wikipedia.org/wiki/Information_hiding). Separation of concerns is a form of [abstraction](https://en.wikipedia.org/wiki/Abstraction_(computer_science)). As with most abstractions, separating concerns means adding additional code interfaces, generally creating more code to be executed. The extra code can result in higher computation costs in some cases, but in other cases also can lead to reuse of more optimized code.
	* Don’t Repeat Yourself (D.R.Y.)
		* Consolidate repeatable code into reusable units
		* ⭐️ Don’t repeat yourself, but also don’t over-abstract.
			* Why? The goal of DRY is to avoid duplication, but it’s important not to take it to the extreme. Be ware of creating tightly coupled code that should have been loosely coupled. Each abstraction should have a clear, single responsibility and be easy to change independently.
			* Strive for a balance:
				* Extract common logic only when you see clear, repeated patterns that are unlikely to diverge.
				* Don’t force unrelated concepts into a single abstraction just to avoid repetition.
				* Prefer clarity (and loose coupling) over cleverness.
			* [Single Source of Truth (SSOT)](https://www.google.com/search?q=Single+Source+of+Truth+(SSOT)) is a better variant of DRY: ensure that every piece of knowledge or logic exists in only one place in your codebase or system. This reduces the risk of inconsistencies and makes maintenance easier.
	* Atomize everything (Principle of Atomicity)
	* [The Unix Philosophy](https://en.wikipedia.org/wiki/Unix_philosophy)
		* Do one thing and do it extremely well.
	* Functions should only do one thing well. Keep functions small.
		* [Make small focused modules for reusability and to make it possible to build larger more advanced things.](https://sindresorhus.com/blog/small-focused-modules)
		* It’s **not about LOC (Lines Of Code)**, but the complexity! ➞ Number of **indentations** is a good metric.

---

# Test everything

* Ensure your code is tested with, tons of “unit tests”, “integration tests”, and some “End to End tests”
* Code should have unit tests before it is approved for merging or refactoring.
* Write lots of automated tests at the granular level, and fewer of them at the higher level.
* Testing shouldn’t be an aftermath, and should be part of your development process.
* Tests you should write:
	* Happy path(s); if everything goes right, does the function work right?
	* Unhappy path(s); does the function properly handle errors or other invalid input?
	* Edge cases; does it correctly handle 0 inputs? null? 1?
	* Scale; does it handle 1,000 inputs correctly? 1,000,000? 1,000,000,000?
	* Regressions; if the function went wrong, write a test to ensure that it doesn’t do it again.
* The Golden Rules of test-driven development (TDD)
	* Don’t build what you can’t test.
	* Write a test before writing the code and focus on writing only the code necessary to pass the test.
	* Test as you build: TDD constantly repeats the steps of adding test cases that fail (no code written yet), passing them with unit testing (code written), and refactoring (code improved)
		* Example in Google Test Framework

			```text
			"System.NotImplementedException: ‘The method or operation is not implemented." → `EXPECT_NO_FATAL_FAILURE(FAIL());`
			```

---

A good developer always writes:

* Simpler code
* Well-documented code
* Well-formatted code
* Performant code
* Secure code

---

#TODO

# [Mistakes engineers make in large established codebases](https://www.seangoedecke.com/large-established-codebases/)

> See also: [Chesterton’s Fence](https://www.google.com/search?q=Chesterton%E2%80%99s+Fence)

* The cardinal mistake is inconsistency. Lack of consistency is the primary long-term killer of large codebases.
* You must resist the urge to make your little corner of the codebase nicer than the rest of it. When you sit down to implement anything in a large codebase, you should always first go and look around for prior art, and follow that if at all possible. If you decide to start a new feature without following existing patterns , you better have a very good reason for it.
	* The main reason is that, as a general rule, large established codebases produce 90% of the value. In any big tech company, the majority of the revenue-producing activity (i.e. the work that actually pays your salary) comes from a large established codebase.
	* The other reason is that you cannot split up a large established codebase without first understanding it.
* Be very, very reluctant to introduce new dependencies. In large codebases, code often lives forever. Dependencies introduce an ongoing cost in security vulnerabilities and package updates that will almost certainly outlive your tenure at the company. If you have to, make sure you pick dependencies that are widely-used and reliable, or that are easy to fork if needed.
* If you ever get the chance to remove code, take it with both hands. This is some of the riskiest work in large codebases, so don’t half-ass it: first instrument the code to identify callers in production and drive them down to zero, so you can be absolutely certain it’s safe to remove. But it’s still worth doing.
