pipeline {
    agent {label 'JDK-11-MVN-PIP-NPM' }
    stages {
        stage ('source code  from git remote repository') {
            steps {
                git url: 'https://github.com/subrAt5238/spring-petclinic.git',
                 branch: 'subrat'
            }
        }
        stage('To build maven package') {
            steps {
                sh 'mvn package'
            }
        }
        stage("archive artifact") {
            steps {
                archiveArtifacts artifacts: 'target/*.jar'
            }
        }
        stage("junit Reports") {
            steps {
                junit '**/surefire-reports/*.xml'
            }
        }
    }
}

