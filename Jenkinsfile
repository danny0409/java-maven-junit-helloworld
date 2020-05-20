pipeline {
  agent any
  stages {
    stage('checkout project') {
      steps {
        checkout scm
        git(url: 'https://github.com/danny0409/java-maven-junit-helloworld.git', branch: 'master', poll: true)
      }
    }

  }
}