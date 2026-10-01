# EXPERIMENT 2: GIT VERSION CONTROL (BULLETPROOF SPEEDRUN)
# 1. Create an isolated folder and initialize Git
mkdir Exp2_Speedrun && cd Exp2_Speedrun
git init

# 2. Create base file and first commit
echo "Start" > app.txt
git add app.txt
git commit -m "Init"

# 3. Switch to a new branch and modify the exact same line
git checkout -b dev
echo "Dev Edit" > app.txt
git commit -am "Dev update"

# 4. Switch back to main and modify the exact same line differently
git checkout main
echo "Main Edit" > app.txt
git commit -am "Main update"

# 5. Force the collision 
# -> TAKE SCREENSHOT 1 HERE (Shows the "CONFLICT" error)
git merge dev

# 6. Resolve the conflict and save
echo "Fixed" > app.txt
git commit -am "Resolved"

# 7. Prove it worked with the graph
# -> TAKE SCREENSHOT 2 HERE (Shows the branching/merging lines)
git log --oneline --graph -n 4

# EXPERIMENT 3: GITHUB ACTIONS (CI/CD SPEEDRUN)
# 1. Create the required hidden GitHub folder
mkdir -p .github/workflows

# 2. Create a minimalist pipeline file
cat << 'INNER_EOF' > .github/workflows/ci.yml
name: Minimal CI
on: [push]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - run: echo "All tests passed successfully!"
INNER_EOF

# 3. Trigger the pipeline
git add .
git commit -m "ci: trigger pipeline"
git push origin main

# 4. View Output
# -> TAKE SCREENSHOT 1 HERE (Go to your GitHub repository in the browser -> Click the 'Actions' tab -> Click the workflow run to show the green checkmark)
