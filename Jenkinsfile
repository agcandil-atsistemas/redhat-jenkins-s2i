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
          sh "docker tag atsistemas/jenkins-2-rhel7:latest registry.atsistemas.com/atsistemas/jenkins-2-rhel7:1.0.0 "
          sh "docker push registry.atsistemas.com/atsistemas/jenkins-2-rhel7:1.0.0 "
          echo 'Publish  OK'
        }
      }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
    }
}
