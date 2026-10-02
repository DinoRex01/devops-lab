# EXPERIMENT 7: PROMETHEUS MONITORING (SPEEDRUN)

# 1. Navigate to the folder
cd /workspaces/devops-lab/Exp7_Prometheus

# 2. Create a minimal Prometheus configuration file
cat << 'INNER_EOF' > prometheus.yml
global:
  scrape_interval: 15s
scrape_configs:
  - job_name: 'prometheus'
    static_configs:
      - targets: ['localhost:9090']
INNER_EOF

# 3. Start the Prometheus monitoring server in the background
docker run -d --name prometheus-exam -p 9090:9090 -v $(pwd)/prometheus.yml:/etc/prometheus/prometheus.yml prom/prometheus

# 4. Wait a few seconds for the server to boot up
sleep 5

# 5. Verify Prometheus is successfully collecting metrics
# -> TAKE SCREENSHOT 1 HERE (Shows the system metrics output)
curl -s http://localhost:9090/metrics | grep "prometheus_build_info"

# 6. Cleanup (Stop and remove the container so it doesn't run forever)
docker stop prometheus-exam && docker rm prometheus-exam
