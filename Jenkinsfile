pipeline{
  agent{label 'master'}
  tools{maven 'M3'}
  stages{
      stage('Checkout'){
          steps{
              git branch: 'main', url: 'https://github.com/mahesh058/SpringPetClinic.git'
      }
    }
    stage('build'){
      steps{
          sh 'mvn compile'
      }
    }
    stage('test'){
      steps{
          sh 'mvn test'
      }
    }
    stage('package'){
      steps{
          sh 'mvn package'
      }
    }
    stage('deploy'){
        steps{
            sh 'java -jar -DServer/.port=8001 spring-petclinic-2.3.1.BUILD-SNAPSHOT.jar'
      }
    }
  }
}
