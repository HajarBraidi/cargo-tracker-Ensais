pipeline {
    agent any

    triggers {
        githubPush()   
    }

    stages {

        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/HajarBraidi/cargo-tracker-Ensais.git'
            }
        }
        //test webhook

        stage('Build & Test with Coverage') {
            steps {
                echo 'mvn clean verify'
            }
        }

    }
//test for webhook
    post {
        success {
            echo 'Build et analyse terminés avec succès !'
        }
        failure {
            echo 'Échec du build ou des tests.'
        }
    }
}
