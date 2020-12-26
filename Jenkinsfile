pipeline {
    tools {
    maven "apache-maven-3.6.3"
    jdk "myjava"
    }
    agent {
        label 'jnlp'
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('package') {
            steps {
                sh 'mvn package'
                stash includes: '**/*.war', name: 'app'
            }
        }
    }
}
