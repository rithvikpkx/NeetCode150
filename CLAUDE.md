# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Role of Claude Code

Claude Code is used **only for repo maintenance**, specifically reformatting problem files to a consistent structure and keeping the README up to date. All solutions, thought processes, and explanations are written by the repo owner. Claude does not write or suggest any code or reasoning.

## What This Repo Is

A personal collection of Blind 75 solutions, written in Java and documented in Markdown. Each problem file captures the full thought process, not just the final answer. The repo is public-facing and recruiter-oriented.

## File Conventions

- Problem files are named in kebab-case: `contains-duplicates.md`
- Files live at the repo root for now (future: may be organized into category folders)
- Each problem file follows this structure:
  1. `# Problem Name | Blind 75 #N` heading
  2. Problem statement
  3. `## Examples` section
  4. `## Thought Process` section (bullet points reasoning through the approach)
  5. `## My Solution` section (fenced Java code block)
  6. `## Explanation` section (step-by-step walkthrough of the code)

## Adding a New Problem

Use the `/add-problem` command. Write a rough `.md` file with your solution and explanation, then run `/add-problem` (or `/add-problem filename.md`) in Claude Code. It will:
1. Reformat the file to the standard structure
2. Update the README badges and progress section automatically

If no filename is passed, it auto-detects the new untracked `.md` file via `git status`.

## README Maintenance

When adding a new solved problem, update `README.md`:

1. **Badge numbers:** increment the `Solved` count
2. **Progress section:** if the problem's category already has a `<details>` block, append a row to its table; if not, add a new `<details>` block for that category
3. The table row format is: `| # | Problem Name | 🟢/🟡/🔴 Difficulty | [View →](filename.md) |`

Difficulty emoji: 🟢 Easy · 🟡 Medium · 🔴 Hard
