pipeline {
    agent any

    triggers {
        githubPush()   // Trigger on GitHub push
    }

    stages {
        stage('Pull Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Aman-ux-source/mywebsite.git',
                    credentialsId: 'github-credentials'
            }
        }

        stage('Deploy Website') {
            steps {
                sh '''
                echo "Deploying website..."
                rm -rf /var/www/html/mywebsite/*
                cp -r * /var/www/html/mywebsite/
                '''
            }
        }
    }
}

