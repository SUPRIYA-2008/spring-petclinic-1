pipeline {
    agent { label 'JDK-17' }
    tools {
        maven 'mvn 3.9'
        jdk 'jdk-17'
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/SUPRIYA-2008/spring-petclinic-1.git',
                    branch: 'main'
            }
        }
        stage('build and package') {
            steps {
                sh script: 'mvn package'
            }
        }
        stage('artifacts') {
            steps {
                archiveArtifacts artifacts: '**/target/spring-petclinic-*.jar'
            }
        }
    }

}
