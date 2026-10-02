# EXPERIMENT 6: DOCKER COMPOSE (SPEEDRUN)

# 1. Navigate to the folder
cd /workspaces/devops-lab/Exp6_DockerCompose

# 2. Create a minimalist docker-compose.yml file
cat << 'INNER_EOF' > docker-compose.yml
version: '3'
services:
  app:
    image: alpine:latest
    command: echo "Docker Compose orchestration successful! Exam passed."
INNER_EOF

# 3. Run Docker Compose
# -> TAKE SCREENSHOT 1 HERE (Shows the container starting and printing the message)
docker-compose up
