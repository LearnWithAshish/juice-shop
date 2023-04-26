pipeline {
    agent any
    stages {
    stage('Install Gitleaks') {
  steps {
    sh 'curl -LO https://github.com/zricethezav/gitleaks/releases/download/v7.6.0/gitleaks-linux-amd64 && sudo chmod +x gitleaks-linux-amd64 && sudo mv gitleaks-linux-amd64 /usr/local/bin/gitleaks'
  }
}
stage('Run Gitleaks') {
  steps {
    dir('git clone https://github.com/LearnWithAshish/juice-shop.git') {
      sh 'gitleaks detect -f json -r /home/ubuntu/juice-shop -v --report=/home/ubuntu/gitleaks/gitleaks.json'
    }
  }
}

}
}
