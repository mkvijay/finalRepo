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
                    finalLib (channel: '#work-test', color: '#00FF00', message: "Build is success (${env.BUILD_URL})")
                }
                failure {
                    finalLib (channel: '#libra-test',  color: '#FF0000', message: "Build failed (${env.BUILD_URL})")
                }
            }
        }
    }
}
