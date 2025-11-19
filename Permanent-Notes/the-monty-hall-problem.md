---
title: The Monty Hall Problem
created: 2025-11-17T09:43:40
modified: 2025-11-19T21:00:06
---

The **Monty Hall Problem (= Car-Goat Problem = 三門問題)** is a famous probability puzzle based on a game show scenario. [^1] A contestant is presented with **three doors**: behind one door is a valuable prize (like a car), and behind the other two are goats. After the contestant selects a door, the host—who **knows what’s behind each door**—opens one of the remaining doors, always revealing a goat. The contestant is then given the choice to **stick with their original door or switch (換？還是不換？)** to the other unopened door. Counterintuitively, the best strategy is to **always switch**, as it gives a **2/3 chance of winning** compared to a **1/3 chance if staying**. The problem illustrates how human intuition about probability can be misleading and highlights the importance of conditional probability in decision-making.

---

# 為何換門更好 

* 第一次選擇：你選擇到汽車的機率是 1/3；選到山羊的機率是 2/3。
* 主持人介入：主持人永遠會打開一扇有山羊的門，這個行動是基於你的第一次選擇。
	* 如果你第一次選擇到的是汽車（機率為 1/3），主持人會隨機打開另一扇有山羊的門。這時，換門一定會讓你輸掉汽車。
	* 如果你第一次選擇到的是山羊（機率為 2/3），主持人就只能打開另一扇有山羊的門。這時，剩下未被打開的門後面一定是汽車，換門一定會讓你贏得汽車。
* 結論：由於你第一次選擇到山羊的機率是 2/3，因此換門贏得汽車的機率是 2/3，而堅持原選擇的機率是 1/3。

[^1]: 是一個源自美國電視節目《Let’s Make a Deal》的機率謎題。
