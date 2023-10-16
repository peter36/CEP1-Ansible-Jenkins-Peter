pipeline{

agent any

stages{

stage('Clone a repo')
{
    steps{

        git branch: 'master', url: 'https://github.com/peter36/CEP1-Ansible-Jenkins-Peter.git'
 }

}

stage('Playbook to Install Maven & Docker')
{
   steps{

ansiblePlaybook credentialsId: 'ansible_credentials', disableHostKeyChecking: true, installation: 'myansible', inventory: 'dev.inv', playbook: 'playbookInstall.yml'

}

}

stage('playbook to build and deploy java app on docker container')

{

steps{

ansiblePlaybook credentialsId: 'ansible_credentials', disableHostKeyChecking: true, installation: 'myansible', inventory: 'dev.inv', playbook: 'playbookDeployment.yml'

}

}

}

}
