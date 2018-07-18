pipeline {  
    agent any
    stages {
        stage("Build") {
            steps {
                echo "Building application..."   
                def antVersion = 'AntDefault'
withEnv( ["ANT_HOME=${tool antVersion}"] ) {
   bat '%ANT_HOME%/bin/ant.bat fetchChanges  deploy'
}
            }
        }
        stage("Unit Tests") {
            steps {
                echo "Unit tests (JUnit)..."
                echo "Mutation tests (pitest)..."

                bat "%ANT_HOME%/bin/ant.bat run-unit-tests"
                bat "%ANT_HOME%/bin/ant.bat run-mutation-tests"
            }
        }
        stage("Functional Test") {
            steps {
                echo "Selenium tests..."
            }
        }
        stage("Performance Test") {
            steps {
                echo "JMeter tests..."
            }
        }
        stage("Quality Analysis") {
            steps {
                echo "Running SonarQube..."
            bat "%ANT_HOME%/bin/ant.bat run-sonarqube-analysis"
            }
        }
        stage("Security Assessment") {
            steps {
                echo "Pen testing..."
            }
        }
        stage("Approval") {
            steps {
                    input "Is the build OK?"
        }
        }
        stage("Deploy") {
            steps {
                echo "Deploying to JBoss 7.2..."
            }
        }
    }
    post {
        always {
        junit '/test/reports/*.xml'
            }
    }       
}
