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
        
    stage('kubernetes Version') {
            steps {
              withKubeConfig([credentialsId: 'kubernetes'          
                    ]) {
                sh 'kubectl get pods'
              //sh "kubectl get node -o wide"
              //archive 'target/*.jar' //so that they can be downloaded later
            }
        }
    
    
    
    }
}
