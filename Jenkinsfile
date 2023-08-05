pipeline{

agent any

stages{

stage('Clone a repo')
{
    steps{

        git branch: 'main', url: 'https://github.com/bazoshimegaelle/CP1-Ansible.git'
 }

}

stage('Playbook to Install Maven & Docker')
{
   steps{

ansiblePlaybook credentialsId: 'ansible_credentials', disableHostKeyChecking: true, installation: 'myansible', inventory: 'Ansible.inv', playbook: 'playbookInstall.yml'

}

}

stage('playbook to build and deploy java app on docker container')

{

steps{

ansiblePlaybook credentialsId: 'ansible_credentials', disableHostKeyChecking: true, installation: 'myansible', inventory: 'Ansible.inv', playbook: 'playbookDeployment.yml'

}

}

}

}


