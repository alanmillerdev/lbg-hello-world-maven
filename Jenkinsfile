pipeline {
    agent any
    
    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "m3"
    }
    
    stages {
        stage('Checkout') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main', url: 'https://github.com/alanmillerdev/lbg-hello-world-maven.git'
            }
        } // <- This closing brace was missing
        
        stage('Compile') {
            steps {
                // Run Maven on a Unix agent.
                sh "mvn clean compile"
            }
        }
        stage('Test')
        {
            steps {
                //Run Maven Tests
                sh "mvn test"
            }
        }
        stage('Package')
        {
            steps {
                sh "mvn -Dmaven.test.skip -Dmaven.compile.skip package"
            }
        }
    }
}