#SE-Git-hw Project documentation
GitHub Homework (SE-Git-hw)

This repository contains a completed set of foundational tasks demonstrating Git version control proficiency, collaborative branch workflows, merge conflict resolutions, and issue tracking protocols aligned with professional software engineering practices.

Workflows Implemented

Global System Configuration
Establishes the developer's identity globally across the system environment.
```bash
git config --global user.name "Stephanie Redd"
git config --global user.email "srredd@pvamu.edu"
```

Feature Branching
Features are developed inside isolated working spaces.
```bash
git checkout -b feature-1
```

Change Propagation (Add, Commit, Push)
```bash
git add .
git commit -m "Initial commit with Hello, World! program"
git push origin main
```

---

Tracked Issues & Resolutions

I utilized **GitHub Issues** to assign, manage, and execute outstanding milestone deliverables across team boundaries.

Issue #1: Update README File Documentation
* **Assignee:** Stephanie Redd
* **Description:** Create structural workspace documentation explaining core workflows.
* **Resolution Method:** Resolved via terminal automation. 
* **Command Executed:**
  ```bash
  git add README.md
  git commit -m "Update documentation, Closes #1"
  git push origin main
  ```

Issue #2: Add Code Comments to apple.py
* **Assignee:** Classmate Collaborator
* **Description:** Comment on the `apple.py` application file with comments explaining the execution.
* **Resolution Method:** Resolved via collaborative branch cross-push.
* **Command Executed:**
  ```bash
  git commit -am "Add descriptive code comments, Fixes #2"
  git push origin main
  ```

---

Troubleshooting

Error: `error: Empty commit message.`
During a manual merge operation conflict resolution (`git merge branch-B`), the default text editor interface was exited cleanly but with an empty commit text header buffer. This threw an error, halting completion and trapping the console inside a structural pending merge loop:
```text
sredd@DESKTOP-0BUDNNK MINGW64 ~/SE-Git-hw (main|MERGING)
\$ git merge branch-B
error: Empty commit message.
Not committing merge; use 'git commit' to complete the merge.
```

Resolution:
Because the tracking files were already scrubbed of conflict flags (`<<<<<<<`, `=======`, `>>>>>>>`), the state simply needed a manual commit flag designation to anchor the merge state and drop out of the `(main|MERGING)` status back into regular tracking:
```bash
git commit -m "Merge branch-B and resolve conflicts"
git push origin main
```
