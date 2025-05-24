pipeline{
    agent any
    tools {
        maven "M3"
    }
    stages {
        stage("Clean Up") {
            steps {
                echo "Cleaning up workspace..."
                deleteDir()
            }
        }
        stage("Clone Repo") {
            steps {
                echo "Cloning Repository..."
                sh "git clone https://github.com/jenkins-docs/simple-java-maven-app.git"
            }
        }
        stage("Build") {
            steps {
                echo "Building the project..."
                dir('simple-java-maven-app') {
                    sh "mvn clean install"
                }
            }
        }
        stage("Test") {
            steps {
                echo "Running tests..."
                dir('simple-java-maven-app') {
                    sh "mvn test"
                }
            }
        }
    }
}