# harness-engineering-starting-template

> harness engineering is the idea that anytime you find an agent makes a mistake, you take the time to engineer a solution such that the agent will not make that mistake again in the future. 
> —— Mitchell Hashimoto

A repository starter template for Agent-assisted / Agent-first development.

## Table of Contents

* [Quick Start](#quick-start)

  * [Shape the Project Idea](#shape-the-project-idea)
  * [Let the Agent Initialize Project Documentation](#let-the-agent-initialize-project-documentation)
  * [Start Development](#start-development)
* [Recommended Structure](#recommended-structure)
* [Development Guide](#development-guide)

  * [Starting Phase](#starting-phase)
  * [Development Phase](#development-phase)
  * [Cleanup Phase](#cleanup-phase)
* [Developer and Agent Responsibilities](#developer-and-agent-responsibilities)
* [Changelog](#changelog)
* [References / Borrowed Materials](#references--borrowed-materials)

## Quick Start

### Shape the Project Idea

At the beginning, you do not need to have every detail of the project fully figured out. You only need to prepare the following information first:

* What problem this project is meant to solve;
* Who the main users are;
* What core features you want it to provide;
* What technology stack you roughly plan to use;
* Whether there is a clear deployment approach;
* Whether there are any constraints that must be followed.

Then let the Agent read the documents in this repository and initialize the project structure based on your project information.

### Let the Agent Initialize Project Documentation

You can use the following prompt:

```markdown
Please read the AGENTS.md file and the docs directory in the current repository.
I want to create a new project based on this template. The project information is as follows:
- Project name:
- Project goal:
- Target users:
- Core features:
- Technology stack:
- Deployment approach:
- Important constraints:

Please do not write a large amount of code directly at first. Instead, improve the project documentation based on the template, including the README, architecture notes, development plan, testing strategy, and Agent working guide.
```

### Start Development

After initialization is complete, it is not recommended to let the Agent complete the entire project in one pass.

A better approach is:

1. Define a small and clear goal first;
2. Ask the Agent to write an execution plan;
3. Let the human confirm the design direction;
4. Let the Agent implement and test;
5. Let the human review key trade-offs and update the experience back into the documentation.

## Recommended Structure

Different projects can be adjusted freely, but it is recommended to keep a similar structure:

Including:

TODO

## Development Guide

Development is flexible. This template only provides a recommended workflow.

### Starting Phase

The focus of the starting phase is to help the Agent understand the project and improve the documentation across the repository. It is recommended to follow [Quick Start](#quick-start).

### Development Phase

As the project goes deeper, the amount of code will gradually increase. At this stage, human developers should not try to review every code detail, but should instead pay more attention to system-level and architecture-level control.

Recommended practices:

* Use a depth-first workflow, breaking large goals into smaller design, implementation, testing, and review modules;
* After completing a branch or a relatively independent small module, start a new Agent session;
* At the beginning of a new session, ask the Agent to read AGENTS.md, relevant docs, and the current task plan first; for most Agents, this should be a default process;
* The human is responsible for confirming the architecture direction, interface boundaries, and product trade-offs;
* The Agent is responsible for concrete implementation, testing, local refactoring, and documentation synchronization;
* After repeated issues are discovered, prioritize updating documentation, tests, or tools instead of only reminding the Agent in chat;
* Perform a weekly cleanup to handle technical debt, outdated documentation, duplicated code, and architecture drift.

### Cleanup Phase

Agent-first development increases code output speed, but it can also amplify bad patterns.

Therefore, it is recommended to perform periodic “cleanup”:

* Delete unused code;
* Merge duplicated logic;
* Update outdated documentation;
* Check whether the directory structure is still reasonable;
* Check whether tests cover critical paths;
* Check whether the Agent repeatedly makes the same kinds of mistakes;
* Write new constraints into AGENTS.md or docs;
* Turn rules that can be mechanically checked into lint, tests, or CI.

## Developer and Agent Responsibilities

Most documents include the division of writing and maintenance responsibilities between the human developer and the Agent.

### The human developer is better suited for

* Project vision;
* Product boundaries;
* User value judgments;
* Architecture design;
* Technology selection trade-offs;
* Safety and privacy baselines;
* Key interface design;
* Acceptance criteria;
* Whether to accept technical debt;
* Whether to merge changes.

### The Agent is better suited for

* Generating initial code based on documentation;
* Implementing local features;
* Writing tests;
* Fixing clearly defined bugs;
* Updating documentation;
* Performing refactoring;
* Summarizing diffs;
* Checking code style;
* Locating problems based on failure logs;
* Modifying PRs based on review feedback.

### Jointly maintained content

* AGENTS.md;
* Architecture documents;
* Development plan;
* Testing strategy;
* Technical debt list;
* Decision records;
* Changelog.

## Changelog

* 2026.06.16 Initial repository setup

## Inspirations

* [Harness Engineering: Using Codex in an Agent-First World](https://openai.com/zh-Hans-CN/index/harness-engineering/)
* [RUNOOB - Harness Engineering](https://www.runoob.com/ai-agent/harness-engineering.html)
* [AGENTS.md](https://agents.md/)
