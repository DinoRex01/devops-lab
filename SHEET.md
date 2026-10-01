# EXPERIMENT 2: GIT SPEEDRUN

# 1. Base commit
echo "Start" > app.txt
git add app.txt
git commit -m "Init"

# 2. Branch edit
git checkout -b dev
echo "Dev Edit" > app.txt
git commit -am "Dev update"

# 3. Main edit
git checkout main
echo "Main Edit" > app.txt
git commit -am "Main update"

# 4. Trigger Conflict
git merge dev

# 5. Resolve
echo "Fixed" > app.txt
git commit -am "Resolved"

# 6. View Graph
git log --oneline --graph -n 4