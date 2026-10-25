# Product brief: Git mystery game

**Owner:** Jameelah Mercer
**Status:** Discovery
**Last updated:** October 24, 2026
**Name:** Working title (`git-mystery-game`)

## Problem

Students are taught basic Git in some classes, but those classes rarely go deeper than the basics. When something goes wrong, like a commit on the wrong branch, work that seems lost, or a secret pushed to a repository, students are left to figure it out through trial and error or scattered pages online.

This project comes from my own experience: I learned Git outside of school, and I always thought these topics deserved more than a random page in a project.

## Hypothesis

Students learn basic Git in class but not how to recover from mistakes, so they rely on trial and error or scattered pages online.

This is a hypothesis, not a finding. A discovery survey in SJSU student club Discords will test it and identify which mistakes are most common.

## Target user

Students who want to build Git skills **before** they need them, in a moment when they have time to learn.

The same student may be in panic mode before a deadline and in curious mode on a free afternoon. This product is for the second moment: learn Git recovery before the panic happens.

## Proposed solution

A browser-based mystery game with time travel. Players solve the mystery by moving through a repository's timeline, and each clue requires a Git skill to uncover.

- **Story drives learning:** commands like `git log`, `git show`, `git reflog`, and `git blame` are the player's investigation tools.
- **Time travel makes Git intuitive:** players visit past moments, uncover erased timelines, and repair the timeline. Git's real safety rules become the rules of the time-travel world.
- **Teach before testing:** each skill is introduced in a short lesson, followed by a quick check, before the player has to use it.
- **Low friction:** players type real Git commands into a simulated terminal in the browser. No install or account required.
- **Visual feedback:** a live commit map shows what each command did.

The first story is planned to follow a new intern the night before launch, replaying the night moment by moment through the repository's history to find out what happened, then repairing the timeline before morning. A later chapter covers security: what to do when a secret is pushed to a repository.

## Goals

1. Players learn to recover from common Git mistakes, measured by improvement between a quiz before and after playing.
2. Players finish what they start, measured by chapter completion.
3. Ship a first chapter to real students and learn from how they play.

## Non-goals

- **Just-in-time help for someone in the middle of a Git mistake.** Those users are well served by search and AI tools, and a story would slow them down.
- **Running real Git in version 1.** The game simulates Git in the browser to remove setup friction. Practicing in a real repository is a possible later feature.
- **Accounts, leaderboards, and daily streaks.** These require a backend and serve long-term daily habits, which a short game doesn't need.

## Success metrics

| Metric | How it's measured |
|---|---|
| Learning gain | Score on a short quiz before playing compared with after |
| Start rate | Share of people who open the game and start chapter 1 |
| Completion | Share of players who finish chapter 1, and where others stop |
| Hint use | Hints used per level, to find levels that are too hard |
| Would recommend | Whether players would recommend it to a classmate |

Targets will be set before launch, once the playtest shows what's realistic.

## Alternatives

| Product | What it does | How this game differs |
|---|---|---|
| Learn Git Branching | Visual lessons on branching concepts | Focuses on recovering from real mistakes, told through a story |
| Oh My Git! | A game for learning Git | Browser-based with no install, and story-driven |
| GitHub Skills | Hands-on courses in real repositories | Lower friction, and built around mistakes and investigation |
| Gitstery | A Git murder mystery played by cloning a repository | Built for beginners, teaches as players go, and runs in the browser. Gitstery is for intermediate users and doesn't teach Git |
| SQL Murder Mystery | Teaches SQL through a mystery | Inspiration for the format, applied to Git |

Gitstery is the closest competitor, so "story-driven" alone isn't a differentiator. The differentiator is the combination: a mystery that teaches beginners, in the browser, focused on recovering from real mistakes. See the [competitive analysis](research/competitive-analysis.md) for details.

## Risks and assumptions

- **Will students play proactively?** This is the riskiest assumption. Start rate and completion at launch will test it.
- **Scope.** A story game is much bigger than a set of levels. Version 1 is one chapter.
- **Story could slow learning.** Scenes stay short, and lessons stay focused on one concept each.
- **Simulated Git isn't real Git.** Some edge cases won't match exactly. Each level ends with commands to practice in a real repository.
- **Small sample.** Early results will come from a few dozen students at most, so they'll be directional, not conclusive.
- **Privacy.** Survey responses and gameplay data are collected anonymously. Raw data stays out of this repository.

## Open questions

- Which Git mistakes are most common for students? (The survey will answer this.)
- Which mistakes should chapter 1 cover?
- How will gameplay data be collected without accounts?
- Is the time travel figurative (a grounded story where Git works like a time machine) or literal (the repository really is a time machine)?
- What should the product be called?

## Next steps

1. Collect discovery survey responses from SJSU club Discords.
2. Add notes from playing each alternative to the competitive analysis.
3. Write the MVP spec for chapter 1 based on survey results.
