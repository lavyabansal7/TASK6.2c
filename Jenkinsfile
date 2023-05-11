pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build the code using Maven'
            }
            post {
                success {
                   emailext attachLog: true,  body: "Build successful", subject: "Build succeeded",  to: 'lavyabansal16@gmail.com'
                }
                failure {
                    mail body: "Build failed", subject: "Build failed",  to: 'lavyabansal16@gmail.com'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Run unit tests using JUnit'
                echo 'Run integration tests using Selenium'
            }
            post {
                success {
                    emailext attachLog: true, body: "Unit and Integration Tests successful", subject: "Unit and Integration Tests successful", to: 'lavyabansal16@gmail.com'
                }
                failure {
                    emailext attachLog: true, body: "Build failed", subject: "Build failed",  to: 'lavyabansal16@gmail.com'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Integrate SonarQube to analyse the code'
            }
            post {
                success {
                    emailext attachLog: true, body: "Code Analysis successful", subject: "Code Analysis successful",  to: 'lavyabansal16@gmail.com'
                }
                failure {
                    emailext attachLog: true, body: "Build failed", subject: "Build failed",  to: 'lavyabansal16@gmail.com'
                }
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
            post {
                success {
                    emailext attachLog: true, body: "Deploy to Staging successful", subject: "Deploy to Staging successful", to: 'lavyabansal16@gmail.com'
                }
                failure {
                    emailext attachLog: true, body: "Build failed", subject: "Build failed",  to: 'lavyabansal16@gmail.com'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Run integration tests on the staging environment using Selenium'
            }
            post {
                success {
                    emailext attachLog: true, body: "Integration Tests on Staging successful", subject: "Integration Tests on Staging successful",  to: 'lavyabansal16@gmail.com'
                }
                failure {
                    emailext attachLog: true, body: "Build failed", subject: "Build failed",  to: 'lavyabansal16@gmail.com'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploy the application to AWS EC2 instance'
            }
            post {
                success {
                    emailext attachLog: true, body: "Deploy to Production successful", subject: "Deploy to Production successful",  to: 'lavyabansal16@gmail.com'
                }
                failure {
                    emailext attachLog: true, body: "Build failed", subject: "Build failed",  to: 'lavyabansal16@gmail.com'
                }
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

