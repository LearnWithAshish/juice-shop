pipeline {
    agent any
    stage('Checkout') {
        // Check out your Git repository
        git 'https://github.com/LearnWithAshish/juice-shop.git'
    }

    stage('Gitleaks') {
        // Run Gitleaks on the repository
        sh 'gitleaks detect -f json -r /home/ubuntu/juice-shop -v'
    }

    // Add more stages as needed
}
