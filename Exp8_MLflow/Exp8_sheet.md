# EXPERIMENT 8: MLFLOW TRACKING (SPEEDRUN)

# 1. Navigate to the folder
cd /workspaces/devops-lab/Exp8_MLflow

# 2. Install MLflow (Takes ~15 seconds)
pip install mlflow

# 3. Create a minimal Python tracking script
cat << 'INNER_EOF' > track.py
import mlflow

# Start a tracking run and log some dummy data
with mlflow.start_run():
    mlflow.log_param("speedrun_mode", "active")
    mlflow.log_metric("exam_score", 100)
    print("MLflow tracking successful! Parameters and metrics logged to local file system.")
INNER_EOF

# 4. Execute the script
python track.py

# 5. Prove the data was recorded locally in the 'mlruns' directory
# -> TAKE SCREENSHOT 1 HERE (Shows the success message and the contents of the generated tracking folder)
ls -la mlruns/0/
