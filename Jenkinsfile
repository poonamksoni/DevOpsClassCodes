pipeline {
    agent none

    tools {
        
        // Install the Maven version configured as "M3" and add it to the path.
        jdk 'myjava'
        maven "mymaven"
    }

    stages {
        stage('Checkout') {
            agent {label 'Linux_slave'}
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/poonamksoni/DevOpsClassCodes.git'

            }
        }
        stage('Compile') {
            agent any
            steps {
                // Get some code from a GitHub repository
                sh 'mvn compile'

            }
        }
        stage('Codereview') {
            agent any
            steps {
                // Get some code from a GitHub repository
                sh 'mvn pmd:pmd'

            }
        }
        stage('UnitTest') {
            agent any
            steps {
                // Get some code from a GitHub repository
                sh 'mvn test'

            }
        }
        stage('MetricCheck') {
            agent any
            steps {
                // Get some code from a GitHub repository
                sh 'mvn cobertura:cobertura -Dcobertura.report.format=xml'

            }
        }
        stage('Package') {
            agent any
            steps {
                // Get some code from a GitHub repository
                sh 'mvn package'

            }
        }
    }
}
