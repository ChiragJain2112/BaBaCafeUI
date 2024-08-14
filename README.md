Gymbot Deployment Guide
This repository contains the codebase for the Gymbot application. Below are the steps to deploy the application on a Google Compute Engine instance.

Table of Contents
Getting Started
Prerequisites
Deployment Steps
1. Logging into Google Cloud
2. Navigating to the Application Directory
3. Pulling the Latest Code
4. Installing Dependencies
5. Building the Application
6. Restarting the Application
Verifying Deployment
Getting Started
This document outlines the steps required to deploy the Gymbot application using the Google Compute Engine. Please ensure you have the necessary permissions and access to the required services before proceeding.

Prerequisites
Access to Google Cloud Console
SSH access to the Compute Engine instance
GitHub repository access
Familiarity with npm or yarn
PM2 installed on the server
Deployment Steps
1. Logging into Google Cloud
Navigate to Google Cloud Console.
Log in with your credentials.
Go to the Compute Engine service.
Click on the SSH button next to your instance to open a terminal.
2. Navigating to the Application Directory
In the SSH terminal, navigate to the application directory:
bash
Copy code
cd /var/www/Gymbot
Verify the directory contents:
bash
Copy code
ls
You should see directories such as PWA, backend, trainerdashboard, frontend, and admin.
3. Pulling the Latest Code
Enter the directory you wish to update:
bash
Copy code
cd <directory_name>
Replace <directory_name> with the desired directory, e.g., backend.
Pull the latest code from the GitHub repository:
bash
Copy code
git pull
4. Installing Dependencies
Based on the lock file present (yarn.lock or package-lock.json), install dependencies:
For npm:
bash
Copy code
npm install --force
For yarn:
bash
Copy code
yarn install
5. Building the Application
After installing dependencies, build the application:
For npm:
bash
Copy code
npm run build
For yarn:
bash
Copy code
yarn build
6. Restarting the Application
Identify the PM2 process ID:
bash
Copy code
pm2 list
Note the ID corresponding to the process you want to restart.
Restart the PM2 process:
bash
Copy code
pm2 restart <process_id>
Replace <process_id> with the actual ID.
Verifying Deployment
After restarting the application, visit the relevant domain to ensure the application is running with the latest changes.

