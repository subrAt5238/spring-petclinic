pipeline {
    agent {label 'MVN-11/8-JDK' }
    stages {
        stage ('source code  from git remote repository') {
            steps {
                git url: 'https://github.com/subrAt5238/spring-petclinic.git',
                 branch: 'qtdev_1'
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

