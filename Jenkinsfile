pipeline {
    agent any
    stages {
        stage ('checkout') {
            steps {
                echo "checking out from github"
checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/sandeep1516/mvn-pro.git']]]
            }
        }
        stage ('Build&test') {
            steps {
                echo "Building and testing..."
            }
        }
        stage ('deploy') {
            steps {
                echo "deploying....."
            }
        }
    }
}

