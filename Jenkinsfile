pipeline {
    agent any
    
    stages {
        stage('Clone') {
            steps {
                // Cette étape permet de récupérer le code source depuis Git
                git 'https://github.com/mustaphadjerdi/essaie.git'
            }
        }
        
        stage('Execute Ansible Playbook') {
            steps {
                script {
                    // Exécute le playbook Ansible
                    sh 'ansible-playbook -i hosts Tp_ansible.yml'
                }
            }
        }
    }
    
    post {
        success {
            echo 'Le playbook Ansible a été exécuté avec succès.'
        }
        failure {
            echo 'L\'exécution du playbook Ansible a échoué.'
        }
    }
}
