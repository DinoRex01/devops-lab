# EXPERIMENT 4: ANSIBLE CONFIGURATION (SPEEDRUN)

# 1. Navigate to the folder
cd /workspaces/devops-lab/Exp4_Ansible

# 2. Install Ansible (Takes ~30 seconds on exam day)
sudo apt-get update && sudo apt-get install -y ansible

# 3. Create a local inventory file (Tells Ansible which servers to target)
echo "localhost ansible_connection=local" > hosts

# 4. Create a minimalist playbook
cat << 'INNER_EOF' > playbook.yml
- hosts: localhost
  tasks:
    - name: Verify Ansible is working
      debug:
        msg: "Ansible configuration successful! Exam ready."
INNER_EOF

# 5. Execute the playbook 
# -> TAKE SCREENSHOT 1 HERE (Shows the green/yellow output and "PLAY RECAP")
ansible-playbook -i hosts playbook.yml
