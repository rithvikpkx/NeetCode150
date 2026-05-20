Refine a newly written problem file to match the repo's standard format, then update README.md to reflect the new progress.

## Step 1: Find the Problem File

If `$ARGUMENTS` is provided, use that as the filename to process.

If no argument is provided, run `git status` to find untracked `.md` files at the repo root, excluding `README.md` and `CLAUDE.md`. That is the file to process.

## Step 2: Reformat the Problem File

Read the file. Rewrite it to match this exact structure, preserving all of the user's reasoning and explanations and only cleaning up formatting, grammar/spelling, and structure:

```
# {Problem Name} | Blind 75 #{N}

{One-sentence problem statement}

## Examples

**Example 1:**

    Input: {input}
    
    Output: {output}


**Example 2:**

    Input: {input}
    
    Output: {output}


## Thought Process

- {Bullet points walking through how to reason about the problem}

## My Solution

\```java
{clean, working Java code}
\```

## Explanation

- {Step-by-step walkthrough of the solution code}
```

Do not simplify, remove, or rewrite the user's thought process or explanation. Only reformat.

**Never use em-dashes (`—`) or hyphens (`-`) as clause or phrase separators in prose.** Use commas, or split into separate sentences instead.

## Step 3: Extract Metadata

From the problem file, determine:
- **Problem name** (e.g., "Contains Duplicate")
- **Problem number** (e.g., 1)
- **Difficulty**: Easy, Medium, or Hard (infer from the problem content if not explicitly stated)
- **NeetCode category** (infer from context if not stated)

Blind 75 categories in order:
Arrays & Hashing · Two Pointers · Sliding Window · Stack · Binary Search · Linked List · Trees · Tries · Heap / Priority Queue · Backtracking · Graphs · Advanced Graphs · 1-D Dynamic Programming · 2-D Dynamic Programming · Greedy · Intervals · Math & Geometry · Bit Manipulation

## Step 4: Update README.md

1. **Increment the Solved badge**: find `Solved-{N}%20%2F%2075` in the badge URL and increment N.
2. **Add to the Progress section**:
   - If a `<details>` block for the category already exists: append a new row to its table and update the summary count (e.g., `1 / 8 solved` → `2 / 8 solved`).
   - If no block for this category exists: insert a new `<details>` block, placed in Blind 75 category order relative to existing blocks.

Table row format:
```
| {N} | {Problem Name} | {emoji} {Difficulty} | [View →]({kebab-case-filename}.md) |
```

Difficulty emoji: 🟢 Easy · 🟡 Medium · 🔴 Hard

## Category Total Problem Counts

Use these for the `X / Y solved` summary line in each `<details>` block:

| Category | Total |
|---|---|
| Arrays & Hashing | 8 |
| Two Pointers | 3 |
| Sliding Window | 4 |
| Stack | 1 |
| Binary Search | 2 |
| Linked List | 6 |
| Trees | 11 |
| Tries | 3 |
| Heap / Priority Queue | 2 |
| Backtracking | 2 |
| Graphs | 6 |
| Advanced Graphs | 1 |
| 1-D Dynamic Programming | 10 |
| 2-D Dynamic Programming | 2 |
| Greedy | 2 |
| Intervals | 5 |
| Math & Geometry | 3 |
| Bit Manipulation | 4 |
