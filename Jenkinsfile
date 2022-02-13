pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
      stage('Docker Build') {
         steps {
            sh label: '', script: 'podman images -a'
            sh label: '', script: '''cd azure-vote/
               podman images -a
               podman build -t jenkins-pipeline .
               podman images -a
               cd ..'''
         }
      }
      
   }
}
