
pipeline {
    options {
        buildDiscarder(logRotator(numToKeepStr: '10', artifactDaysToKeepStr: '7', artifactNumToKeepStr: '5'))
    }

    parameters {
        string(name: 'slaveNodeLinux', defaultValue: 'xld', description: 'Node label where steps would be executed.')
        string(name: 'slaveNodeWindows', defaultValue: 'windows-jdk11', description: 'Node label where steps would be executed.')
        string(name: 'jdkVersion', defaultValue: 'OpenJDK 11.0.12', description: 'JDK version.')
        string(name: 'slackRoom', defaultValue: 'mario-build-monitor', description: 'Slack room. Used for notifications')
    }

    stages {

        stage('Say hello on main branch') {
            when {
                expression {
                    env.BRANCH_NAME == 'main'
                }
            }
            steps {
                sh "echo Hello"
            }
        }

        stage('Say hello on develop branch') {
            when {
                expression {
                    env.BRANCH_NAME == 'develop'
                }
            }
            steps {
                sh "echo Hello"
            }
        }
    }
}