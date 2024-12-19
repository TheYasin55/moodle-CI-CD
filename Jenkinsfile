pipeline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = "false"
    }

    stages {
        stage('Run Ansible Playbook v2') {
            steps {
                echo 'Ansible Playbook for up apache server'
                sh '''
                ansible-playbook -i localhost, -c local deploy.yml --become
                '''
            }
        }
    }

    post {
        failure {
            echo 'Deployment Failed.'
        }
        success {
            echo 'Deployment Successful.'
        }
    }
}
