pipeline {
    agent any
    stages {
      stage('s2i') {
        steps {
          echo "branch name: $BRANCH_NAME"
          sh "ls -alsh"
          sh "s2i build https://github.com/agcandil-atsistemas/redhat-jenkins-s2i registry.access.redhat.com/openshift3/jenkins-2-rhel7 atsistemas/jenkins-2-rhel7 --network host"

        }
      }
      stage('Publish in Nexus') {
        when{
          expression {
              return !env.BRANCH_NAME.startsWith("feature")
          }
        }
        steps {

          echo 'Publish  '
        }
      }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
    }
}
