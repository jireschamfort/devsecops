pipeline {
  agent any

  stages {
      stage('Build Artifact') {
            steps {
              sh "mvn clean package -DskipTests=true"
              archive 'target/*.jar' //so that they can be downloaded later
            }
        } 
    stage('Java Version') {
            steps {
              sh "java -version"
              //archive 'target/*.jar' //so that they can be downloaded later
            }
        }   
    }
}
