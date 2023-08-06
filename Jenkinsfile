pipeline {
    agent { label 'JDK-17' }
    tools {
        jdk 'jdk-17'
        maven 'maven 3.9'
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
        stage('reporting') {
            steps {
                archiveArtifacts artifacts: '**/target/springpetclinic-*.jar'
                junit testResults: '**/target/surefire-reports/TEST-*.xml'
            }
        }
    }

}
