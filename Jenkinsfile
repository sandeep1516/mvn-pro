pipeline {
    agent any
    
    stages {
         stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }
         
        stage ('checkout') {
            steps {
                echo "checking out from github"
checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/sandeep1516/mvn-pro.git']]]
            }
        }
        stage ('Build&test') {
            steps {
                echo "Building and testing..."
                sh '/usr/local/maven/bin/mvn clean install'
            }
        }
        stage ('deploy') {
            steps {
                echo "deploying....."
            }
        }
    }
}

