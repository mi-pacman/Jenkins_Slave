pipeline {
  agent {label 'Ubuntu'}

  stages {
    stage('Packer - Build Ubuntu Image') {
      steps {
        sh """
        #!/bin/bash
        pwd
        ls
        packer build Jenkins_Slave/jenkins-slave.pkr.hcl
        """
      }
    }
    stage('Docker - Verify Ubuntu Image') {
      steps {
        sh """
        #!/bin/bash
        ls packer/artifacts/qemu
        """
      }
    }
  }
}