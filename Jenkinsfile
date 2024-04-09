pipeline {
    agent {
        label 'test-server'
    }
    stages {
        stage('Install Ansible') {
            steps {
                script {
                    // Install Ansible on the remote server
                    sshCommand remoteUser: 'jenkinsworker', remoteHost: '192.168.0.112', command: 'sudo yum install -y ansible'
                }

            }
        }
        stage('Verify Ansible Installation') {
            steps {
                sh 'ansible --version'
                sh 'echo ============================================'
                sh 'Ansible is successfully installed on Test server.'
            }
        }
    }
}
