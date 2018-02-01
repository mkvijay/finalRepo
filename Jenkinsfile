#!groovy
@Library('my-shared-library') _

pipeline {
    agent any

    stages {
        stage ('Compile Stage') {
            steps {
                echo 'Hello first'
            }
        }
        stage ('Testing Stage') {
            
            steps {
                echo 'Hello Second'
            }
        }
        stage ('Deployment Stage') {
            steps {
                echo 'Hello Third'
            }
            post {
                success {
                    finalLib (slack_channel: '#work-test', email: 'vijay45kmar@gmail.com', color: '#00FF00', message: "Build is success (${env.BUILD_URL})", subject: "${env.service} Pipeline Notification")
                }
                failure {
                    finalLib (slack_channel: '#libra-test',  color: '#FF0000', message: "Build failed (${env.BUILD_URL})")
                }
            }
        }
    }
}
