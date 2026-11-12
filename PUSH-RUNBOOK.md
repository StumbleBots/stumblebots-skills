# Push Runbook: stumblebots-skills

This repository was built locally in push-ready form. No GitHub account exists yet for StumbleBots, and nothing has been pushed. The steps below are the exact remaining steps once Jon creates the GitHub account. Account creation is Jon's step and takes about 5 minutes. No agent creates an account in Jon's name.

Repo-local git identity is already set in this folder: user.name is StumbleBots and user.email is hello@stumblebots.com. That is a project domain identity and it is adjustable. Change it before the first commit if Jon wants a different name or email on the commit.

## Step 1: Jon creates the GitHub account (about 5 minutes, his step)

1. Create the GitHub account Jon wants to own this library.
2. Confirm the account username. The remote URL in Step 3 uses that username exactly.

No other setup is needed before the push. Do not create a repository in the web UI with a README, license, or gitignore, because this folder already carries all three and an auto-created file would conflict on push. If a repository is created in the web UI, create it completely empty.

## Step 2: Initial commit (run from this folder)

Run these commands from the skills-repo folder, which is:

~/workspace/goals/earning-more-money/hidden_files/at-phase1/skills-repo/

```
cd ~/workspace/goals/earning-more-money/hidden_files/at-phase1/skills-repo/
git status
git add -A
git status
git commit -m "StumbleBots skills: five instruction-only starters for one-person businesses"
git log --oneline -1
git branch -M main
```

Notes:

- git init was already run here and the default branch is main. The git branch -M main line is safe to run again if the branch name needs to be forced to main.
- All files should already be staged from the build. The git add -A line is a safety pass so nothing new is missed.
- Verify the commit contains exactly these paths before pushing: README.md, LICENSE, .gitignore, PUSH-RUNBOOK.md, and skills/lead-hunter/SKILL.md, skills/sales-follow-up/SKILL.md, skills/support-triager/SKILL.md, skills/meeting-prepper/SKILL.md, skills/inbox-drafter/SKILL.md. No scripts or executable files belong in this repo.

## Step 3: Create the public repository and push

Create the public repository named stumblebots-skills under the new account. Use one of the two routes below.

Route A, with the GitHub CLI, signed in as the new account:

```
gh repo create stumblebots-skills --public --source=. --remote=origin --push
```

Route B, manual, if the CLI is not available:

1. On github.com, create a new repository named stumblebots-skills, set to Public, with no README, no license, and no gitignore added.
2. Back in this folder, add the remote and push. Replace <github-owner> with the new account username exactly:

```
git remote add origin https://github.com/<github-owner>/stumblebots-skills.git
git push -u origin main
```

After the push, open the repository page signed out and confirm all five SKILL.md files are visible under skills/ and the README renders with its table.

## Step 4: skills.sh verification

skills.sh indexes public skills shipped through the skills CLI or public GitHub repositories and ranks by install telemetry. Indexing is not instant and it is not guaranteed by the push alone, so verify it directly.

1. Go to skills.sh and search for each of the five skill names, one at a time:
   - lead-hunter
   - sales-follow-up
   - support-triager
   - meeting-prepper
   - inbox-drafter
2. Search skills.sh for the repository itself: search for stumblebots-skills and for StumbleBots.
3. For each search, record what was found or not found, with the date checked.
4. Try the install path the README promises: run npx skills add <github-owner>/stumblebots-skills in a clean test folder and record whether the CLI lists the five skills.
5. Record all findings with dates in ATP2-STATUS.md, in the at-phase1 folder one level above this repository folder. Name the file checked and the exact search terms used for any not found result, so an absence claim carries its method.

Repeat the skills.sh searches daily until indexing is verified or the day 7 kill line below fires.

## Kill line

if indexing cannot be verified within 7 days of the repository going public, the (c) leg is declared unproven in writing and the test reverts to (b) alone under the same bars.

Apply that line exactly as written. Whoever verifies indexing, or fails to verify it by day 7, writes the outcome into ATP2-STATUS.md the same day.

## ATP2 clock

The ATP2 clock starts the day the wedge is live on the site AND this repo is public. Both conditions must be true. The clock does not start on the push alone if the wedge pages are not yet live, and it does not start on the site alone if this repo is not yet public.

Whoever lands the push records that date in ATP2-STATUS.md and sets the day-7 and day-14 check jobs named there. Per ATP2-STATUS.md, those jobs are:

1. Day 7 check (runonce, clock start + 7 days): skills.sh indexing state and metrics read (registry installs, wedge page copies from the Abacus counters, signup count, referral sources). This check also carries the build-phase kill line above.
2. Day 14 verdict read (runonce, clock start + 14 days): read the locked bars recorded in ATP2-STATUS.md.

Set both jobs with owner goal earning-more-money, reporting to the CEO chat, at the time the clock start date is recorded. Do not set them before the clock start date is known.
