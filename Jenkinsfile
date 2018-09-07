pipeline {
    agent any
    stages {
      stage('s2i') {
        agent {
            docker { image 'registry.access.redhat.com/rhscl/s2i-core-rhel7' }
        }
        steps {
          echo "branch name: $BRANCH_NAME"
          sh "ls -alsh"
          sh "s2i build . registry.access.redhat.com/openshift3/jenkins-2-rhel7 atsistemas/jenkins-2-rhel7"

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
