---
allowed-tools: Bash(git status), Bash(git add:*), Bash(git commit:*), Bash(gh issue close:*), Bash(gh issue comment:*)
description: Complete current work - commit changes and close GitHub issue
---

Complete the current task:

1. Run `git status` to see all changes
2. Stage relevant files with `git add`
3. Create a descriptive commit message summarizing the work done
4. If an issue number is provided ($ARGUMENTS), close it with a summary comment:
   - `gh issue close $ARGUMENTS --repo chaoming/ww2-flutter-game --comment "Completed: <summary>"`
5. If no issue number provided, just commit the changes
6. Show a summary of what was completed
