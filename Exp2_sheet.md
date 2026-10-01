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
