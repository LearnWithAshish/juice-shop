pipeline {
    agent any
    stages {
    stage('Install Gitleaks') {
  steps {
    sh '''#!/bin/bash
        curl -LO https://github.com/zricethezav/gitleaks/releases/download/v7.6.0/gitleaks-linux-amd64 && chmod +x gitleaks-linux-amd64 && sudo mv gitleaks-linux-amd64 /usr/local/bin/gitleaks && gitleaks --version
    '''
  }
}
  stage('Run Gitleaks') {
  steps {
    dir('https://github.com/LearnWithAshish/juice-shop.git') {
      sh '''#!/bin/bash
          sudo gitleaks detect -f json -r https://github.com/LearnWithAshish/juice-shop.git -v --report=/home/ubuntu/gitleaks/gitleaks.json
          exit 0
         '''
        }
    }
  }
  stage('Dependency-Check') {
  steps {
    dir('https://github.com/LearnWithAshish/juice-shop.git') {
      sh '''#!/bin/bash
      cd /home/ubuntu/dependency-check/bin
          ./dependency-check.sh --project dep-check-pipeline --scan 'home/ubuntu/juice-shop' -f html  --out /home/ubuntu/gitleaks/dep-check.html
           '''
          }
          }
          }
  }
}

