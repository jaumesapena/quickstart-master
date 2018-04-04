pipeline {
  agent any
  stages {
    stage('Preparation') {
      steps {
        git(url: 'https://github.com/wildfly/quickstart.git', branch: 'master')
      }
    }
    stage('Build') {
      steps {
        bat 'bat(/"${mvnHome}\\bin\\mvn" -Dmaven.test.failure.ignore clean package/)'
      }
    }
    stage('Deploy') {
      steps {
        bat 'bat \'"C:/Users/jsapena/Desktop/wildfly-10.1.0.Final/bin/jboss-cli.bat" --connect --command="deploy helloworld/target/helloworld.war"\''
      }
    }
  }
  environment {
    mvnHome = 'tool \'maven jenkins\''
  }
}