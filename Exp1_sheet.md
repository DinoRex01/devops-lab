# Experiment 1: Agile Project Lifecycle (Jira & GitHub Integration)
# (SPEEDRUN TIME: ~5 minutes)

## Part 1: Browser Setup (Jira)
1. Create a **Scrum** project (Team-managed).
2. Go to **Backlog**, create an **Epic** ("User Auth System") and a **Story** ("Email Login").
3. **CRITICAL: WRITE DOWN THE TICKET ID** (e.g., DEV-1).
4. Drag the Story to **Sprint 1** and click **Start Sprint**.
   # -> TAKE SCREENSHOT 1: Active Sprint Board showing the ticket in "To Do"
5. Go to **Apps -> Explore more apps**, install **GitHub for Jira**.
6. Configure it to only access your `devops-lab` repository.

## Part 2: Terminal Execution (Codespace)
# 1. Navigate to the experiment folder
cd /workspaces/devops-lab/Exp1_Agile_Jira

# 2. Simulate development work
echo "def login(): pass" > login.py
git add login.py

# 3. Commit using the EXACT Jira Ticket ID
# REPLACE DEV-1 WITH YOUR ACTUAL TICKET ID!
git commit -m "DEV-1: Add login route"

# 4. Push to GitHub to trigger the webhook
git push origin main
# -> TAKE SCREENSHOT 2: Terminal showing successful push

## Part 3: Verification (Jira)
1. Go back to your Jira board.
2. Click on the ticket (e.g., DEV-1).
3. Look under the **Development** panel on the right.
4. Click on the **1 commit** link to open the details pop-up.
   # -> TAKE SCREENSHOT 3: Pop-up showing the linked GitHub commit inside Jira
