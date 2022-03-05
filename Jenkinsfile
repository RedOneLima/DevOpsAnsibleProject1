pipeline {
  agent any
  stages {  
    // Execute when branch = 'main'
    stage("WAR deployment") {
      when {
        branch 'main'
      }
      steps {
        ansiColor('xterm') {
          ansiblePlaybook( 
          playbook: './ansible/playbook.yaml',
          inventory: './ansible/hosts.yaml', 
          credentialsId: 'Ansible-Controller-Private-Key',
          vaultCredentialsId: 'ansible-vault-pass',
          become: true,
          colorized: true) 
        }
      }
    }
  }
}