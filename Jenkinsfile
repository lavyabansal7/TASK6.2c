pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build the code using Maven'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Run unit tests using JUnit'
                echo 'Run integration tests using Selenium'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Integrate SonarQube to analyse the code'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Perform security scan using OWASP ZAP'
            }
            post {
                success {
                    emailext attachLog: true, body: "Security Scan successful", subject: "Security Scan successful",  to: 'lavyabansal16@gmail.com'
                }
                failure {
                    emailext attachLog: true, body: "Build failed", subject: "Build failed",  to: 'lavyabansal16@gmail.com'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploy the application to AWS EC2 instance'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Run integration tests on the staging environment using Selenium'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploy the application to AWS EC2 instance'
            }
        }
    }

    post {
                success {
                    emailext attachLog: true, body: "overall Build was successful", subject: "overall Build was successful",  to: 'lavyabansal16@gmail.com'
                }
                failure {
                    emailext attachLog: true, body: "overall Build failed", subject: "Build failed",  to: 'lavyabansal16@gmail.com'
                }
            }
}

