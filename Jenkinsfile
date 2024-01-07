pipeline {
 agent {
    node {
      label 'workstation'
    }
  }
 parameters {
     choice(name: 'env', choices: ['dev', 'prod'], description: 'Pick environment')
     string(name: 'component', defaultValue: '', description: 'component name')
     string(name: 'app_version', defaultValue: '', description: 'App Version to deploy')
   }
    stages {

       stage('Ansible') {
         steps {
           sh 'ansible-playbook -i ${component}-${env}.rdveopsb72.store, roboshop.yml -e ansible_user=centos -e ansible_password=DevOps321 -e env=${env} -e role_name=${component}'
         }
       }

     }

     post {
       always {
         cleanWs()
       }
     }

   }