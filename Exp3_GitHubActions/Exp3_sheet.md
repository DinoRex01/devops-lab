# EXPERIMENT 3: GITHUB ACTIONS (CI/CD SPEEDRUN)
# NOTE: GitHub Actions MUST be created in the root folder, not in a subfolder.

# 1. Go to root and create the hidden GitHub folder
cd /workspaces/devops-lab
mkdir -p .github/workflows

# 2. Create the pipeline file
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
git commit -m "ci: trigger pipeline for experiment 3"
git push origin main
