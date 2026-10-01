# EXPERIMENT 5: DOCKER CONTAINERIZATION (SPEEDRUN)

# 1. Navigate to the folder
cd /workspaces/devops-lab/Exp5_Docker

# 2. Create a minimalist Dockerfile
cat << 'INNER_EOF' > Dockerfile
FROM alpine:latest
CMD ["echo", "Docker container built and running successfully! Exam passed."]
INNER_EOF

# 3. Build the Docker image
# -> TAKE SCREENSHOT 1 HERE (Shows the build process and success message)
docker build -t exam-app .

# 4. Run the container 
# -> TAKE SCREENSHOT 2 HERE (Shows the text output from inside the isolated container)
docker run exam-app
