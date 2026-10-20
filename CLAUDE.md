# Claude Instructions for this project

## Project

**Landing page for a Spoken Word show.**

Objective: let users find out more about the event and book a free seat.

## Git & deployment

Never run `git push` or force-push under any circumstances. Commit changes locally, then stop. Tell the user the commits are ready and wait for them to push.

When the user asks to create a PR, push the branch and open the PR with `gh pr create`.

Never work directly on the main branch. Always work in a git worktree on a separate branch. If a worktree is not already active, create one before making any changes.

Never delete pages, files, database records, or table data without explicit approval from the user. If a deletion seems necessary as part of a solution, explain why and wait for a yes before removing anything.

## Planning before coding

Always present a plan before writing or changing any code. Do not start implementing until the user has explicitly approved the plan.

When presenting a plan:

- Explain what you are going to do in plain, non-technical language that a non-technical product manager can understand.
- If there are multiple possible approaches, describe each one briefly and explain the tradeoff (what you gain, what you give up, and why it matters for this project).
- Clearly state which approach you are recommending and the reason — not just "it's cleaner" but what practical problem it solves or what risk it avoids.
- Keep it short. Bullet points are fine. The goal is a decision, not a lecture.
