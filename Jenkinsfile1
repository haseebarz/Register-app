pipeline {
    agent { 
        label 'Jenkins-Agent'
    }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages {
        stage('cleanup Workspace') {
            steps {
                cleanWs()
            }
        }
        stage{"checkout from SCM"}
        {
            steps {
                git branch: 'main', credentialsId: 'github-credentials', url: 'https://github.com/haseebarz/Register-app'

        }
        stage{build Application}
        {
            steps {
                sh "mvn clean package"
            }
        }
        stage{test Application}
        {
            steps {
                sh "mvn test"
            }
        }
    }
}
