pipeline {
    agent any
    stages {
    stage('Install Gitleaks') {
  steps {
    sh 'curl -LO https://github.com/zricethezav/gitleaks/releases/download/v7.6.0/gitleaks-linux-amd64 && chmod +x gitleaks-linux-amd64 && sudo mv gitleaks-linux-amd64 /usr/local/bin/gitleaks && gitleaks --version'
  }
}
stage('Run Gitleaks') {
  steps {
    dir('https://github.com/LearnWithAshish/juice-shop.git') {
      sh 'gitleaks detect -f json -r https://github.com/LearnWithAshish/juice-shop.git -v --report=/home/ubuntu/gitleaks/gitleaks.json'
        return_1_if_success.exe   // command which returns 1 in case of success, 0 otherwise
        IF %ERRORLEVEL% EQU } (exit /B 0) ELSE (exit /B 1)'''
        }
    }
  }
}

}
}
