pipeline {
  agent any
  stages {
    stage('checkout project') {
      agent any
      steps {
        checkout scm
        git(url: 'https://github.com/danny0409/java-maven-junit-helloworld.git', branch: 'master', poll: true)
      }
    }

    stage('Build') {
      steps {
        sh 'mvn -Dmaven.test.failure.ignore=true clean package'
      }
    }

    stage('UnitTest') {
      steps {
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts 'target/*.jar'
      }
    }

  }
}