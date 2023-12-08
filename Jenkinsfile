pipeline {
  agent {
   node {
    label 'workstation'
   }
  }
 }
  parameters {
    choice(name: 'env', choices('dev','prod') description: 'pickup environment' )
    string(name: 'component' default_name: '' description: 'pickup component_name' )
 }

   options {
   ansicolor(xterm)
   }

   stage 'ANSIBLE' {
   step {
   sh 'ansible-pull -i loaclhost, -U roboshop.yml -e username=centos -e password=DevOps321 -e env=${env} -e role_name=${component_name}
   }
   }
   post {
   always {
   clear ws()
   }
