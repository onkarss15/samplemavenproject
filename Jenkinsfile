pipeline {
   agent any
 tools {
      // Install the Maven version configured as "M3" and add it to the path.
      maven "MAVEN_HOME"
   }
   stages {
      stage('Git checkout') {
         steps {
            echo 'I am in git checkout'
            git 'https://github.com/arbiswas1990/samplemavenproject.git'
         }
      }
      stage('Build') {
         steps {
            echo 'I am in build stage'
            sh '''
            cd samplemvnwar
            mvn clean package
            '''
         }
      }
     
   }
}
