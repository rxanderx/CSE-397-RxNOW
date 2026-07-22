# White paper Agile Engineering Methods

## Title: Comparative Analysis of Lean, Extreme Programming (XP), and Test-Driven Development (TDD), with Pair vs Mob Programming
**Name:** Kelson Gneiting
**Course/Semester/Section**: CSE 397 Professional Career Projects: Fall 2024: Section 31
**Instructor**: Brother Clements
**Date**: July 21, 2026

## Summary:
This paper compares Lean-style simplicity, XP engineering discipline, and TDD quality practices, then evaluates collaboration models (Pair vs Mob). The sources agree that rapid feedback, small increments, and shared understanding improve software quality. The key tradeoff is effort cost: practices that raise quality can reduce speed on simple tasks.

## Introduction:
The goal was to examine modern alternatives to heavyweight development by focusing on XP, TDD, and collaborative programming methods. Research included wiki references, a technical video, an industry website, and a scholarly paper to balance theory and evidence. XP directly targets change by using short cycles: it "attempts to reduce the cost of changes in requirements by having multiple short development cycles" (Wikipedia, Source 1).

## Definitions:
- Lean: A development mindset focused on minimizing waste, shortening feedback loops, and delivering customer value quickly.
- Extreme Programming (XP): An Agile method centered on disciplined engineering practices, rapid feedback, and simplicity.
- Test-Driven Development (TDD): A practice where tests are written before production code, typically in a red-green-refactor cycle.
- Pair Programming: Two developers work together at one workstation using driver and navigator roles.
- Mob Programming: The full team collaborates on one task with one active keyboard and shared direction.

## Overview:
XP emerged in the 1990s and emphasizes disciplined engineering practices, with Agile Alliance defining it as a framework that "aims to produce higher quality software and higher quality of life for the development team" (Agile Alliance, Source 3). It promotes simplicity, feedback, and continuous integration.

TDD operationalizes quality through tests-first development. As the video source explains, "you describe the behavior of your code before you go and implement it" and then repeat "red green refactor" cycles (Fireship YouTube, Source 2).

Pair and Mob programming focus on real-time collaboration. In pairing, "the driver writes code while the other, the observer or navigator, reviews each line" (Wikipedia, Source 1), while mob programming scales this to "one team - one (active) keyboard - one screen" (Wikipedia, Source 1).

## Strength and Weakness:
XP strength: consistent feedback and adaptability; "if it hurts, do it more often" captures its continuous-improvement mindset (Agile Alliance, Source 3). XP weakness: requires team discipline and customer engagement to work well.

TDD strength: fewer regressions, clearer requirements, safer refactoring. TDD weakness: can be misused as a metric game, since "100% code coverage doesn't mean that you have a good test suite" (Fireship YouTube, Source 2).

Pair programming strength: quality and learning; research shows it "helps to decrease the number of software defects" (Kattan et al., Source 4). Weakness: higher labor cost because pairs "spent more work hours compared to two developers working alone" (Kattan et al., Source 4), and productivity can drop for simple tasks.

Mob programming strength: broad shared understanding across coding, testing, and design. Weakness: coordination overhead and social risks such as "Groupthink" that can suppress better alternatives (Kattan et al., Source 4).

## Usage and Applicability:
- Where is it used?
XP and TDD are common in Agile product teams, startups, and CI/CD environments. Pair programming is common for complex stories, onboarding, and high-risk code. Mob programming is used when teams need deep alignment across architecture, testing, and delivery.

- When would it be used?
Use XP when requirements change quickly and frequent releases are required. Use TDD when correctness and maintainability are high priorities. Use Pair programming for difficult or unfamiliar tasks, and Mob programming when the main problem is poor shared understanding across the team.

## Comparison:
- Lean vs XP:
Lean emphasizes waste reduction and flow; XP specifies concrete engineering practices (pairing, CI, test-first, refactoring).
- XP vs TDD:
TDD is a specific coding/testing practice; XP is a full method that includes TDD plus collaboration and planning values.
- Pair vs Mob:
Pair has lower coordination overhead and is usually easier to schedule; Mob maximizes knowledge diffusion but can slow execution if facilitation is weak.

Alternatives include Scrum-only implementation (without engineering practices), solo programming with code review, and feature-branch workflows with delayed integration.

## Summary:
The best practical stack for many teams is XP principles, TDD for critical logic, and selective Pair/Mob use based on task complexity. Use Pair when precision and mentorship are needed, and use Mob to resolve alignment gaps across the team. Keep Lean simplicity as a filter: build only what is needed now, then improve through fast feedback loops.

## References:
1. LLM: GitHub Copilot (GPT-5.3-Codex), analytical synthesis and comparative interpretation, generated July 21, 2026.
2. Wiki: Wikipedia - Pair programming, Extreme programming, Team programming. https://en.wikipedia.org/wiki/Pair_programming ; https://en.wikipedia.org/wiki/Extreme_programming ; https://en.wikipedia.org/wiki/Team_programming
3. Video: Fireship, TDD and testing strategies. https://www.youtube.com/watch?v=Jv2uxzhPFl4
4. Scholarly paper (primary source): Kattan et al., "Swarm or pair?: strengths and weaknesses of pair programming and mob programming," ACM. https://dl.acm.org/doi/abs/10.1145/3234152.3234169
5. Website: Agile Alliance, "What is Extreme Programming?" https://agilealliance.org/glossary/xp/
