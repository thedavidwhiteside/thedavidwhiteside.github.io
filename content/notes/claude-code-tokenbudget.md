---
title: "Claude Code Token Budget Plugin"
date: 2026-04-25T12:00:00Z
draft: false
tags: ["AI", "ClaudeCode"]
---

[claude-code-tokenbudget](https://github.com/thedavidwhiteside/claude-code-tokenbudget) was just released.  There currently isn't a good mechanism for preventing cost overruns with Claude Code if your using AWS Bedrock for example as a backend.  I ran into a few accidental cost overruns, this plugin will help you prevent accidental cost overages.

Its easy to install, give it a try.

```bash
claude plugin marketplace add thedavidwhiteside/claude-code-tokenbudget
claude plugin install tokenbudget@claude-code-tokenbudget
```