pipeline {
  agent {
    node {
      label 'dev'
    }

  }
  stages {
    stage('Code Quality Check') {
      steps {
        sh '''sonar-scanner \\
  -Dsonar.projectKey=easy-school \\
  -Dsonar.sources=. \\
  -Dsonar.host.url=http://18.232.31.116:9000 \\
  -Dsonar.login=sqp_365a742f46c43e1d2e92c5a66de5114193801cad'''
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
