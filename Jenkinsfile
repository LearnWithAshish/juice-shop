pipeline {
  agent any
  stages {
    stage('Check-git-scerets')
    steps(
      sh 'git clone https://github.com/LearnWithAshish/juice-shop.git'
      sh 'gitleaks detect -f json -r /home/ubuntu/juice-shop -v --report=/home/ubuntu/gitleaks/gitleaks.json'
      
          }
    }
      }
    }
