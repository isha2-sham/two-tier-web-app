 stage('Deploy') {
    steps {
        sshagent(['ec2-ssh-key']) {
            sh """
                ssh -o StrictHostKeyChecking=no ubuntu@your-ec2-ip '
                    cd /home/ubuntu/myproject &&
                    git pull origin main &&
                    docker compose down &&
                    docker compose up -d --build
                '
            """
        }
        echo "Deployed to EC2 ✅"
    }
}
