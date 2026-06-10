What authentication methods does gh support?


### 🔹 1) Browser-based OAuth login (default)

```bash
gh auth login
```

* Opens browser for GitHub login
* Uses **OAuth authentication**
* Most common and easiest method

👉 *Best for normal users*

---

### 🔹 2) Personal Access Token (PAT)

```bash
gh auth login --with-token
```

* You manually provide a **GitHub token**
* Useful for:

  * automation
  * CI/CD pipelines

👉 *Best for scripts and secure automation*

---

### 🔹 3) SSH authentication

* Uses your **existing SSH keys**

```bash
gh auth login
# choose SSH when prompted
```

* Works with Git operations over SSH

👉 *Best for developers already using SSH*

---

### 🔹 4) GitHub Enterprise authentication

* Supports login to **enterprise servers**

```bash
gh auth login --hostname <enterprise-url>
```

👉 *Used in corporate environments*

---

## 🔑 Final interview one-liner

> GitHub CLI supports authentication via browser-based OAuth, personal access tokens, SSH keys, and GitHub Enterprise login for organizational setups.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

How could you use gh issue in a script or automation?
## ✅ Using `gh issue` in scripts/automation — Interview style

---

## 🔹 1) Automate issue creation (CI/CD alerts)

Create issues automatically when something fails:

```bash id="4f2vpg"
gh issue create \
  --title "Build Failed" \
  --body "CI pipeline failed. Check logs." \
  --label "bug"
```

👉 Used in:

* CI/CD pipelines (GitHub Actions, Jenkins)
* Monitoring alerts

---

## 🔹 2) Create issues from scripts

Example Bash script:

```bash id="94bqjc"
#!/bin/bash

ERROR_LOG="App crashed at $(date)"

gh issue create \
  --title "Production Error" \
  --body "$ERROR_LOG" \
  --label "urgent"
```

👉 Automatically logs production issues

---

## 🔹 3) Auto-close issues after deployment

```bash id="4vrclp"
gh issue close 12 --comment "Fixed and deployed to production"
```

👉 Used in:

* Deployment pipelines
* Release automation

---

## 🔹 4) Use with GitHub Actions

Example workflow step:

```bash id="mggkj5"
- name: Create issue on failure
  if: failure()
  run: |
    gh issue create \
      --title "Pipeline Failed" \
      --body "Check GitHub Actions logs" \
      --label "bug"
```

👉 Requires:

```bash id="ivyx98"
GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

---

## 🔹 5) Query issues for automation

```bash id="djoklb"
gh issue list --label "bug" --state open
```

👉 Used for:

* dashboards
* reporting
* automation decisions

---

## 🧠 Real-world use cases

* 🚨 Auto-create issue when server crashes
* 🔄 Close issue after successful deployment
* 📊 Generate reports of open bugs
* 🔁 Sync issues with external tools

---

## 🔑 Interview one-liner

> `gh issue` can be used in scripts and CI/CD pipelines to automate issue creation, updates, and closure based on events like build failures, deployments, or monitoring alerts.




-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## ✅ 1) What merge methods does `gh pr merge` support?

### 🔹 Supported methods

```bash
gh pr merge --merge     # default
gh pr merge --squash
gh pr merge --rebase
```

### 🔍 Explanation

* **`--merge`**

  * Creates a **merge commit**
  * Preserves full history

* **`--squash`**

  * Combines all commits into **one commit**
  * Keeps history clean (most commonly used)

* **`--rebase`**

  * Reapplies commits on top of base branch
  * Creates **linear history without merge commit**

---

### ⚡ Extra useful flags

```bash
gh pr merge --delete-branch
gh pr merge --auto
```

* `--delete-branch` → removes feature branch after merge
* `--auto` → enables auto-merge when checks pass

---

## 🧠 Interview one-liner

> `gh pr merge` supports merge commit, squash, and rebase strategies, allowing flexibility between preserving history and maintaining a clean linear history.

---

## ✅ 2) How would you review someone else's PR using `gh`?

---

### 🔹 Step 1: List PRs

```bash
gh pr list
```

---

### 🔹 Step 2: View PR details

```bash
gh pr view <pr-number>
```

👉 Shows:

* description
* commits
* status checks

---

### 🔹 Step 3: Checkout PR locally

```bash
gh pr checkout <pr-number>
```

👉 Lets you:

* run code
* test changes

---

### 🔹 Step 4: View changes (diff)

```bash
gh pr diff <pr-number>
```

---

### 🔹 Step 5: Add review (approve/comment/request changes)

```bash
gh pr review <pr-number> --approve
```

```bash
gh pr review <pr-number> --comment -b "Looks good"
```

```bash
gh pr review <pr-number> --request-changes -b "Fix issue in API logic"
```

---

## 🧠 Interview one-liner

> To review a PR using `gh`, I would list PRs, view details, check out the branch locally, inspect the diff, and then approve or request changes using `gh pr review`.

---

## 🔥 Real-world flow (what good engineers say)

> I usually check out the PR locally, run tests, review diffs using `gh pr diff`, and then approve or request changes using `gh pr review`.



--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## ✅ List workflow runs using GitHub CLI (`gh`)

---

## 🔹 Basic command (any public repo)

```bash id="x0npw1"
gh run list --repo <owner>/<repo>
```

---

### 🔹 Example

```bash id="rjqqr7"
gh run list --repo actions/starter-workflows
```

👉 This shows:

* Workflow name
* Status (success, failure, in progress)
* Branch
* Event (push, PR, etc.)
* Run ID

---

## 🔧 Filter results

### Show only latest runs

```bash id="kf9syc"
gh run list --limit 5 --repo actions/starter-workflows
```

### Filter by status

```bash id="ikdf3d"
gh run list --status success --repo actions/starter-workflows
```

---

## 🔍 View details of a run

```bash id="w7x95t"
gh run view <run-id> --repo actions/starter-workflows
```

---

## 🧠 Interview one-liner

> You can list GitHub Actions workflow runs using `gh run list --repo owner/repo`, and inspect specific runs using `gh run view`.

---

## ⚡ Pro tip

If you're inside the repo locally:

```bash id="e9yq8d"
gh run list

no need to specify --repo


-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## ✅ How `gh run` and `gh workflow` are useful in CI/CD pipelines (Interview style)

---

## 🔹 1) Monitor pipeline status (`gh run`)

```bash
gh run list
gh run view <run-id>
```

👉 Use cases:

* Check if builds are **passing or failing**
* Monitor deployment status in real-time
* Debug failed pipelines via logs

---

## 🔹 2) Debug failures quickly

```bash
gh run view <run-id> --log
```

👉 Helps:

* Identify errors without opening GitHub UI
* Speeds up troubleshooting in production pipelines

---

## 🔹 3) Re-run failed workflows

```bash
gh run rerun <run-id>
```

👉 Use cases:

* Retry flaky tests
* Re-run deployments after fixing issues

---

## 🔹 4) Trigger workflows manually (`gh workflow`)

```bash
gh workflow run <workflow-name>
```

👉 Use cases:

* Trigger **manual deployments**
* Run pipelines on demand (e.g., hotfix release)

---

## 🔹 5) Automate deployments

```bash
gh workflow run deploy.yml
```

👉 Used in:

* CD pipelines to deploy apps
* Infrastructure automation

---

## 🔹 6) Integrate into scripts

Example:

```bash
if gh run list --limit 1 | grep failure; then
  echo "Pipeline failed, creating alert..."
fi
```

👉 Used for:

* Alerts
* Monitoring systems
* Auto-remediation

---

## 🔹 7) CI/CD visibility in terminal

* No need to open browser
* Faster DevOps workflows
* Works well in remote servers / SSH sessions

---

## 🧠 Real-world usage

* 🚀 Trigger deployment from terminal
* 🔍 Debug failed build instantly
* 🔁 Re-run pipeline after fix
* 📊 Monitor CI health

---

## 🔑 Interview one-liner

> `gh run` and `gh workflow` allow developers to monitor, trigger, and manage CI/CD pipelines directly from the terminal, enabling faster debugging, automation, and deployment workflows.

---

## ⚡ Strong answer (to impress interviewer)

> In CI/CD pipelines, I use `gh run` to monitor and debug workflow executions, and `gh workflow` to trigger deployments or jobs programmatically, which helps automate and speed up the development and release process without relying on the UI.

---




