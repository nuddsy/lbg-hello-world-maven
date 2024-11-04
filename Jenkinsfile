pipeline {
        agent any
        
        tools {
            //Install Maven as M3 (we did it earlier)
            maven "M3"
        }
        
        stages {
            stage('Checkout') {
                steps {
                    //Code from GitHub
                    
                    git branch: 'main', url: 'https://github.com/nuddsy/lbg-hello-world-maven.git'
                }
            }
            stage('Compile') {
                steps {
                    //Run Maven on Unix agent
                    sh "mvn clean compile"
                }
            }
            stage('Test') {
                steps {
                    sh "mvn -Dmaven.compile.skip test"
                }
            }
            stage('Package') {
                steps {
                    sh "mvn -Dmaven.test.skip -Dmaven.compile.skip package"
                }
            }
        }
}