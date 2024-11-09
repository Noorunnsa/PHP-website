pipeline {
    agent any

   environment {
       ANSIBLE_INVENTORY = '/home/jenkinsmaster/PHP-website/inventory.yml'
   }
   stages {
       stage('git checkout') {
           steps {
               checkout scmGit(branches: [[name: '*/Job2']], extensions: [], userRemoteConfigs: [[ url: 'https://github.com/Noorunnsa/PHP-website.git']])
           }
       }
    
        stage('execute playbook') {
           steps {
               script
                       {
                   sh 'pwd'
                   sh 'ansible-playbook -i $ANSIBLE_INVENTORY "/var/lib/jenkins/workspace/Install Docker - Job2/playbook.yml"'
                       }
           }
         }
     }
   }
