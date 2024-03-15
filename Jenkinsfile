pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/orlandCasta/jenkins-test'
            }
        }
        stage('Build') {
            steps {
                sshagent(['ssh-agent']) {
                    //sh 'ssh -tt -o StrictHostKeyChecking=no ubuntu@3.133.148.116 ls'
                    sh "scp -r ./* ubuntu@3.133.148.116:/home/ubuntu"
                }
            }
        }
        // stage('Run Server') {
        //     steps {
        //         // Connect to the server via SSH and start your Node.js application
        //         script {
        //             sshagent(['ssh-agent']) {
        //                 // sh "ssh ubuntu@52.14.61.66 'cd /home/ubuntu && yarn install && node server.js'"
        //                 sh "ssh ubuntu@3.138.118.117 'whoami && node --version && ls'"
        //             }
        //         }
        //     }
        // }
    }
}