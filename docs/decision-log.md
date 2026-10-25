# Decision log

The major decisions on this project: the options considered, what was chosen and why, and what would cause each decision to be revisited. Decisions 1–6 were made during early planning and recorded here in October 2026.

---

## 1. Combine Git and security into one game, with Git first

**Status:** Accepted

**Context:** There were two game ideas: one about fixing Git mistakes, and one about securing a repository (leaked secrets, `.gitignore`, outdated dependencies).

**Options considered:**
- Two separate games
- One game with Git and security combined

**Decision:** One game. Git mistakes come first, and security becomes a later chapter. A level about pushing a secret connects the two.

**Why:**
- Security lessons make the most sense inside Git. A leaked API key is a Git mistake with consequences, and it's easier to understand once players know how Git history works.
- The launch audience is small. Splitting players across two games would leave too little data on each to learn from.
- Both games would need the same engine, so building it once and adding chapters is far less work.
- Starting with Git reaches more students, since everyone uses Git.

**Tradeoffs:** Players who only care about security have to start with Git. The security chapter should be playable on its own for people who already know Git.

**Revisit if:** The discovery survey shows two distinct audiences, such as beginners wanting Git help while experienced students only care about security.

---

## 2. Simulate Git in the browser instead of running real Git

**Status:** Accepted

**Context:** Players need a way to type Git commands and see the results.

**Options considered:**
- Simulate Git in the browser with a JavaScript model of the repository
- Use a JavaScript library that implements Git in the browser
- Have players download a broken repository and fix it with real Git, with a script that checks the fix
- Open a cloud environment with real Git, such as GitHub Codespaces

**Decision:** Simulate Git in the browser for version 1. Practicing in a real repository through Codespaces is a possible later feature.

**Why:**
- Lowest friction: players open a link and start, with no install and no account.
- Full control over each scenario, so every level starts the same way.
- The game can check whether the player's final repository is correct, not whether they typed specific commands. Most Git problems have several valid fixes, and accepting any correct fix teaches better.

**Tradeoffs:** It isn't real Git, so some edge cases won't behave exactly the same. Each level ends with commands to practice in a real repository.

**Revisit if:** Players ask for real-repository practice, or the simulation's differences from real Git confuse them.

---

## 3. Borrow some of Duolingo's game mechanics, but not all

**Status:** Accepted

**Context:** Duolingo is a strong example of making learning feel like a game. Its mechanics are designed for daily habits over months, while this game is a set of levels players finish in an hour or two.

**Options considered:**
- Adopt Duolingo's mechanics broadly
- Choose only the mechanics that serve this game's learning goal

**Decision:**
- **Borrowed:** short lessons, a progress path of levels that unlock in order, immediate feedback after each command, review of earlier concepts in later levels, and small celebrations on finishing a level.
- **Rejected:** hearts, where mistakes cost a life, as well as streaks and leagues.
- **Instead of hearts:** stars, where using hints costs a star.

**Why:**
- In Git, experimenting is how people learn, and fear of breaking things is part of the problem this game addresses. Hearts would punish exploration and teach the opposite of the goal.
- Streaks and leagues drive daily return visits over months, which a short game doesn't need. They also require accounts and a server.
- Stars reward understanding without punishing experimentation.

**Revisit if:** A version with more content makes return visits matter, or playtesting shows players need more structure.

---

## 4. Target proactive learners, and make quick-fix users a non-goal

**Status:** Accepted

**Context:** Two kinds of people might use a Git learning tool: students who want to build skills before they need them, and people in the middle of a Git emergency who want a fix now.

**Options considered:**
- Design for both groups
- Design for proactive learners only

**Decision:** Target students who want to learn Git recovery before they need it. Just-in-time help is a non-goal.

**Why:**
- People in the middle of a mistake are well served by search engines, Stack Overflow, and AI tools, which answer in seconds.
- A story would stand between them and their fix, so serving them would likely weaken the game without beating existing tools.
- The same student can be in panic mode before a deadline and in curious mode on a free afternoon. The game is for the second moment: learn before the panic happens.

**Tradeoffs:** This bets that enough students will play a learning game when nothing is forcing them to. That's the riskiest assumption in the project.

**Revisit if:** Few people who open the game start or finish chapter 1.

---

## 5. Teach each concept before testing it

**Status:** Accepted

**Context:** In the first prototype, players were dropped into tasks that assumed they already knew Git. Reviewing the prototype showed there was nothing teaching players what they needed before they were tested on it.

**Options considered:**
- Rely on hints only
- Add a command reference only
- Add a short lesson before each level

**Decision:** Each level starts with a short lesson: a few concept cards with before-and-after commit maps, followed by one quick-check question. While playing, a command reference stays visible, and players can reopen the lesson anytime without losing progress. Hints still cost stars.

**Why:**
- Teaching before testing is how effective learning games work. Duolingo introduces a word before asking players to use it.
- Before-and-after maps show what a command does before players have to use it.
- Separating free learning (lessons and reference) from paid nudges (hints) keeps stars meaningful.

**Tradeoffs:** Lessons add time before the action starts. Players who already know the material can skip them.

**Revisit if:** Playtesters skip lessons and then struggle, or find the lessons too long.

---

## 6. Move toward a story-driven mystery format

**Status:** Accepted direction, to be tested in playtesting

**Context:** The prototype is a set of standalone levels. The goal is a game-based product that's engaging as well as educational, inspired by puzzle games like Blue Prince and Agent A and by RPGs.

**Options considered:**
- Standalone levels, as in the prototype
- A mystery story where Git commands are the player's investigation tools

**Decision:** Build a text-based mystery. Players piece together what happened from a repository's history, and each clue requires a Git skill. The first story, *Launch Night*, follows a new intern the night before launch. Version 1 is one chapter, and the existing levels become part of it.

**Why:**
- Git history is evidence. Commits record who changed what, when, and why, so commands like `git log`, `git show`, `git blame`, and `git reflog` work naturally as detective tools.
- A story gives proactive learners a reason to keep playing.
- Lessons can be delivered inside the story, such as a mentor's notes or a coworker's message.
- Staying text-based keeps the scope achievable for one person.

**Tradeoffs:** A story game is much bigger than a set of levels, since it adds writing, pacing, and puzzle design. A story could also slow down learning.

**Revisit if:** Playtesting shows the story lowers completion or quiz scores compared with standalone levels.

---

## 7. Combine the mystery with time travel

**Status:** Accepted
**Date:** October 24, 2026
**Builds on:** #6

**Context:** After choosing a mystery format, other themes were considered to see whether a different gameplay concept would map onto Git better, including a garden, a rail network, a writers' room, and time travel. Time travel was the strongest fit for Git's concepts, especially recovering from mistakes.

**Options considered:**
- Mystery only
- A different theme, such as a garden, rail network, or writers' room
- Mystery combined with time travel

**Decision:** Combine the mystery with time travel. Players solve the mystery by moving through the repository's timeline: investigating history, visiting past moments, uncovering erased timelines, and repairing the timeline. Players still type real Git commands, and the time-travel theme shapes the story and visuals.

**Why:**
- Investigating Git history already is moving through time, so time travel gives the mystery a mechanic instead of adding a second premise.
- Git's safety rules become the rules of the time-travel world. Visiting the past is safe. Changing the past without creating a timeline (committing in detached HEAD without a branch) means losing that work. Rewinding erases the future, but the reflog remembers. Rewriting a timeline others have seen causes paradoxes, which is why reverting is safer than resetting on shared branches.
- Time travel fits recovery from mistakes, the game's core topic, better than the other themes considered.
- Players keep typing real commands, so nothing has to be translated back into real Git.

**Tradeoffs:** Combining two concepts could muddle the story if the time-travel elements aren't tied tightly to Git.

**Open question:** Is the time travel figurative (a grounded story where Git works like a time machine) or literal (the repository really is a time machine in the story)?

**Revisit if:** Playtesters find the time-travel framing confusing, or it makes it harder to connect what they learn to real Git.

---

## Template for new decisions

Add new decisions at the bottom with the next number. If a decision changes, add a new entry and mark the old one "Superseded by #N" instead of editing it.

```markdown
## N. Short title of the decision

**Status:** Proposed / Accepted / Superseded by #N

**Context:** What situation or question led to this decision?

**Options considered:**
- Option A
- Option B

**Decision:** What was chosen.

**Why:** The reasons.

**Tradeoffs:** What this costs or risks.

**Revisit if:** What evidence would change this decision.
```
