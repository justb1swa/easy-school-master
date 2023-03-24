pipeline {
  agent {
    node {
      label 'Dev'
    }

  }
  stages {
    stage('Code Quality Check') {
      steps {
        sh '''sonar-scanner \\
  -Dsonar.projectKey=easy-school \\
  -Dsonar.sources=. \\
  -Dsonar.host.url=http://52.206.217.129:9000 \\
  -Dsonar.login=sqp_e111820a7d7744089b55de30e6d2639800c09646'''
      }
    }

    stage('Build') {
      steps {
        sh 'rm -rf easy-school/'
        sh 'git clone https://github.com/teammira2023/easy-school.git'
        sh 'chmod +x easy-school/runtime.sh'
        sh 'easy-school/runtime.sh'
      }
    }

  }
}