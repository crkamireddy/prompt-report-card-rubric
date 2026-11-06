# Prompt Report Card

A rubric for grading agent prompts: instructions that run on their own, again and again,
with nobody watching. That means system prompts, subagents, skills, scheduled or
overnight agents, and custom GPTs. A gap in a one-off chat prompt gets fixed by the next
message. A gap in an agent prompt repeats on every run until someone notices.

It gives a letter grade and explains what would earn a higher one. It deliberately
doesn't rewrite your prompt for you. It names what's missing and what goes wrong because
of it, and leaves the wording to you. It grades one-off prompts too.

## The rubric

**[RUBRIC.md](RUBRIC.md)** is the whole grader. It covers the grader's role, its two hard
rules (diagnose, don't prescribe; never invent flaws), eight weighted dimensions, a
catalog of common mistakes, the grade scale, and how the review should be written.

It's plain text written for a model to follow, but it reads fine as a human checklist too.

## Ways to use it

**In your browser.** Paste a prompt, get a report card. Free, uses your own Claude
account:
https://claude.ai/artifact/YWEWXd9VY5FnXwExHHhnP5

**Read the rubric as a web page:**
https://claude.ai/artifact/1bdMptwZpdTxPqhgx2sxoN

**In Claude Code.** Clone this repo, open it with `claude`, and run:

```
/grade You are a helpful assistant that summarizes support tickets...
```

`/grade` reads `RUBRIC.md` fresh every time, so if you edit the rubric your changes
apply right away. It also keeps a small local log in `history/` (grades and weak spots,
never your prompt text) and points out once the same weakness keeps coming back.

**Anywhere else.** Paste `RUBRIC.md` into any capable model as its instructions, then
give it the prompt to grade.

## Checking the grader hasn't drifted

`examples/` holds five made-up prompts, from strong to weak, with their agreed grades in
`examples/expected.json`. The grades are kept in a separate file so the grader can't see
the answers first. After editing the rubric, `/calibrate` re-grades all five and
reports any that moved, and why.

These five are part of a larger answer key of 21 prompts. The other 16 stay private
because they came from friends and family or from other people's published work.

## Sources

Built from Anthropic's
[Prompting best practices](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices)
and
[The new rules of context engineering for Claude 5 generation models](https://claude.com/blog/the-new-rules-of-context-engineering-for-claude-5-generation-models),
with OpenAI's and Google's prompting guidance cross-checked. The sources are credited
in the rubric itself.

## License

[CC BY 4.0](LICENSE). You can reuse and adapt this, including commercially, as long as
you credit Cat Kamireddy and link back here.

Made by [Cat Kamireddy](https://catkamireddy.com).
