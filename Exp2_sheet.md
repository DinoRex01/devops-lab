# EXPERIMENT 2: GIT VERSION CONTROL 
mkdir Exp2_Speedrun && cd Exp2_Speedrun
git init
echo "Start" > app.txt
git add app.txt
git commit -m "Init"
git checkout -b dev
echo "Dev Edit" > app.txt
git commit -am "Dev update"
git checkout main
echo "Main Edit" > app.txt
git commit -am "Main update"
git merge dev
echo "Fixed" > app.txt
git commit -am "Resolved"
git log --oneline --graph -n 4
