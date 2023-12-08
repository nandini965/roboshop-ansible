pipeline {
  agent {
   node {
    label 'workstation'
   }
  }

  parameters {
    choice(name: 'env', choices('dev','prod') description: 'pick environment' )
    string(name: 'component' default_name: '' description:  'component_name' )
 }

   options {
   ansicolor(xterm)
   }

   stage 'ANSIBLE' {
   steps {
   sh 'ansible-playbook -i ${component}.${env}.rdevopsb72.store, roboshop.yml -e ansible_user=centos -e ansible_password=DevOps321 -e env=${env} -e role_name=${component_name}'
   }
   }
   post {
   always {
   clear ws()
   }
   }
}