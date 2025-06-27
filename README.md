Test Jenkins integration
📄 2. README.md Contents (Both Repos)
Each README.md should include:

✅ Project Overview
Brief description of what the app does (e.g., Flask API, Express UI).

✅ Prerequisites
markdown
Copy
Edit
- Node.js (v16 or v18 recommended)
- Python 3.10+
- Jenkins
- PM2
- GitHub account
✅ EC2 Setup Instructions
markdown
Copy
Edit
# On Ubuntu EC2
sudo apt update
sudo apt install -y python3-pip nodejs npm git
npm install -g pm2
✅ Jenkins Setup
Install Jenkins on EC2.

Start Jenkins: sudo systemctl start jenkins

Enable Jenkins: sudo systemctl enable jenkins

✅ Jenkins Configuration
Plugins to install: Git, Pipeline, NodeJS, Python.

Global Tools:

NodeJS (NodeJS_LTS): Install automatically

Python (Python3): /usr/bin/python3

✅ Jenkinsfile Explanation
Each stage: Clone, Install, Test, Deploy

✅ How to Trigger Build
markdown
Copy
Edit
- Push code to GitHub
- Webhook triggers Jenkins
✅ Access URLs
markdown
Copy
Edit
🌐 Live Access URLs
Flask App: http://13.233.29.76:5000

Express App: http://13.233.29.76:3000 
🖼️ 3. Screenshots (Required)
Make sure to capture and include the following:

✅ Jenkins Build Console Output

Green checkmark build with all stages passed

✅ pm2 list

bash
Copy
Edit
pm2 ls
✅ Browser Screenshots

Flask App at :5000

Express App at :3000

✅ GitHub Webhook Trigger Log
(optional, but helpful)
