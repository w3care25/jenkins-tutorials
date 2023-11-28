pipeline {
  agent any
  stages {
    stage('step-one') {
      steps {
        echo 'step 1'
      }
    }

    stage('step-two') {
      steps {
        echo 'step2'
      }
    }

    stage('step-three') {
      steps {
        echo 'Step 3'
      }
    }

    stage('step-four') {
      steps {
        sh '''#!/bin/bash

# Check if Node.js is already installed
if ! command -v node &> /dev/null; then
    # If not installed, install Node.js using a package manager (assuming apt)
    echo "Node.js is not installed. Installing..."
    sudo apt update
    sudo apt install -y nodejs
else
    echo "Node.js is already installed."
fi

# Check if npm (Node Package Manager) is installed
if ! command -v npm &> /dev/null; then
    # If not installed, install npm
    echo "npm is not installed. Installing..."
    sudo apt install -y npm
else
    echo "npm is already installed."
fi

# Navigate to the directory where you want to run the demo server
cd /path/to/your/demo/server

# Install project dependencies (assuming a package.json file is present)
npm install

# Run the demo server
npm start

# Print a message indicating the server is running
echo "Demo server is now running. You can access it at http://localhost:3000/"
'''
      }
    }

  }
}