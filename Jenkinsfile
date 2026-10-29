
pipeline {
    agent any

    tools {
        maven 'MAVEN-HOME'
    }

    stages {
        stage('Git Repo & Clean') {
            steps {
                bat 'if exist mavenjava rmdir /s /q mavenjava'
                bat 'git clone https://github.com/09lakshya/mavenjava.git'
                bat 'mvn -f mavenjava/pom.xml clean'
            }
        }

        stage('Install') {
            steps {
                bat 'mvn -f mavenjava/pom.xml install'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn -f mavenjava/pom.xml test'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn -f mavenjava/pom.xml package'
            }
        }
    }
}
