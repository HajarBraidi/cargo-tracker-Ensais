pipeline {
    agent any

    triggers {
        githubPush()   
    }

    stages {

        stage('Clone') {
            steps {
                git branch: 'develop', url: 'https://github.com/HajarBraidi/cargo-tracker-Ensais.git'
            }
        }

        stage('Build & Test with Coverage') {
            steps {
                echo 'mvn clean verifyy'
            }
        }

    }
//
    post {
        success {
            echo 'Build et analyse terminés avec succès !'
        }
        failure {
            echo 'Échec du build ou des tests.'
        }
    }
}
