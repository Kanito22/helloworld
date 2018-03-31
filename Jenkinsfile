node {
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/Kanito22/helloworld.git'
      stash 'helloworld'
   }
   stage('Deploy') {
      unstash 'helloworld'
      sh "ansible-galaxy install -r requirements.yml"
      sh "ansible-playbook -i ./hosts playbook.yml"
   }
}
