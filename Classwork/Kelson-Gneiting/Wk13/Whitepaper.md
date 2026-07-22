# White paper Code Quality Engineering

## Title: Comparative Analysis of Static Program Analysis, Automated Testing (Jest/Selenium), and Hybrid Linter Intelligence (Checkstyle+)
**Name:** Kelson Gneiting
**Course/Semester/Section**: CSE 397 Professional Career Projects: Fall 2024: Section 31
**Instructor**: Brother Clements
**Date**: July 21, 2026

## Summary:
This paper compares three core code-quality approaches: static analysis, automated testing frameworks, and LLM-augmented linting. The evidence shows no single method is sufficient. The strongest workflow combines static checks for early defect discovery, automated tests for behavior validation, and targeted AI support for nuanced style and documentation rules.

## Introduction:
The purpose of this research is to evaluate practical tools and methods that improve code quality while controlling technical debt. The research examined one wiki source, one scholarly paper, one technical video transcript, and one tool-documentation comparison. The baseline concept is that static analysis is "performed without executing" code (Wikipedia, Source 1), while testing validates behavior during execution.

## Definitions:
- Static Program Analysis: Inspection of source or object code without running the program.
- Linter: A rule-based static analysis tool that enforces coding conventions and catches structural issues.
- Automated Testing: Programmatic verification of expected behavior through unit, integration, and end-to-end tests.
- Jest: A JavaScript-focused testing framework for unit and integration-style workflows.
- Selenium: A browser automation tool used for end-to-end testing via WebDriver commands.
- Hybrid Linting: Combining deterministic lint rules with LLM reasoning for context-sensitive style checks.

## Overview:
Static analysis has become foundational in safety and security workflows because it detects problems before runtime. As Source 1 defines, static analysis is "the analysis of computer programs performed without executing them" (Wikipedia, Source 1). It is also widely used for secure engineering and critical systems.

Automated testing complements this by validating runtime behavior. Source 3 emphasizes software complexity: "Software is dynamic with a lot of moving parts and requirements that evolve over time" (Fireship transcript, Source 3). Modern pipelines therefore combine unit, integration, and end-to-end testing levels.

The latest evolution is hybrid linting. Source 2 notes that classic linters are rigid and that nuanced style rules can fall outside standard checks; the proposed solution is a hybrid where LLM reasoning is "invoked only for specific rules" requiring deeper interpretation (Checkstyle+ paper, Source 2).

## Strength and Weakness:
Static analysis strength: early detection and scale across large codebases. Weakness: theoretical limits; "finding all possible run-time errors... is undecidable" (Wikipedia, Source 1), so false positives or blind spots are unavoidable.

Automated testing strength: behavior confidence across code changes, especially with layered test strategies. As Source 3 notes, "Test driven development is scientifically proven to reduce defects" (Fireship transcript, Source 3). Weakness: higher initial effort and execution/runtime cost.

Jest strength: fast developer feedback and simple mocking, supported by "a custom resolver for imports" (Jest docs, Source 4). Weakness: ecosystem concentration in JavaScript/TypeScript contexts.

Selenium strength: realistic browser-level validation across environments; it "can send standard Python commands to different browsers" (PyPI Selenium docs, Source 4). Weakness: slower, more brittle tests and greater maintenance overhead than unit tests.

Hybrid linter strength: better detection of subtle violations. Source 2 reports high detection quality with "1,434 true positives" and minimal error rates (Checkstyle+ paper, Source 2). Weakness: higher latency and API cost compared to pure static rule engines.

## Usage and Applicability:
- Where is it used?
Static analysis is used in CI pipelines, secure SDLC programs, and safety-critical software domains. Jest is common in frontend/backend JavaScript projects. Selenium is used in cross-browser QA automation and release regression suites. Hybrid linting fits quality-focused teams managing large codebases and technical debt.

- When would it be used?
Use static analysis on every commit for fast prevention. Use Jest for frequent unit/integration feedback during development. Use Selenium for critical user journeys before release. Use hybrid linting when naming, documentation, and semantic style quality are recurring review bottlenecks.

## Comparison:
- Static analysis vs automated testing:
Static analysis is earlier and cheaper per run; tests provide stronger behavioral guarantees.
- Jest vs Selenium:
Jest optimizes speed and developer iteration; Selenium optimizes real browser fidelity.
- Rule-based linting vs hybrid linting:
Rule-based linting is predictable and cheap; hybrid linting catches context-sensitive violations better but adds cost and latency.

Alternatives include SonarQube, ESLint, PyTest, Playwright, and mutation-testing tools for stronger test-suite quality analysis.

## Summary:
The most effective code-quality strategy is layered: static analysis first, automated tests second, and hybrid linting for nuanced language-quality gaps. This approach balances speed, precision, and maintainability. Recommendation: standardize deterministic checks in CI, reserve heavy browser tests for release gates, and apply LLM-augmented linting selectively where conventional rules repeatedly miss important issues.

## References:
1. LLM: GitHub Copilot (GPT-5.3-Codex), comparative synthesis and technical analysis, generated July 21, 2026.
2. Wiki: Wikipedia, "Static program analysis." https://en.wikipedia.org/wiki/Static_program_analysis
3. Video: Fireship, "Automated Testing in 100 Seconds" (transcript-based analysis).
4. Scholarly paper (primary source): Checkstyle+, "Reducing Technical Debt Through The Use of Linters with LLMs." https://arxiv.org/abs/2510.23068
5. Website: Jest documentation. https://jestjs.io
6. Website: Selenium documentation (PyPI). https://pypi.org/project/selenium/
7. Website: Jest vs Selenium. Https://knapsackpro.com/testing_frameworks/difference_between/jest/vs/selenium