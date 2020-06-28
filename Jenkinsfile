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
            cd /var/lib/jenkins/workspace/testpipe/samplemvnwar
            mvn clean package
            '''
         }
      }
      stage('Deploy') {
         steps {
            echo 'I am in Deploy stage'
            deploy adapters: [tomcat7(credentialsId: 'tomcat access', path: '', url: 'http://15.206.66.135:9090')], contextPath: 'DevOpsOnline', war: '**/*.war'
         }
      }
   }
}
