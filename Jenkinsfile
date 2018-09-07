pipeline {
    agent {
        docker { image 'registry.access.redhat.com/rhscl/s2i-core-rhel7' }
    }
    stages {
      stage('s2i') {
        steps {
          echo "branch name: $BRANCH_NAME"
          sh "ls -alsh"
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
