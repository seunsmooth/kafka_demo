pipeline {

    agent any

   stages {

    stages {
      stage('CleanWorkspace') {
            steps {
                cleanWs()
            }
            
      stage('verify-replication-factor') {
          steps {
              sh "${env.WORKSPACE}/verify-replication-factor.sh ${env.WORKSPACE}/descriptor.yaml 3"
          }
      }
      
      stage('verify-num-of-partitions') {
          steps {
              sh "${env.WORKSPACE}/verify-num-of-partitions.sh ${env.WORKSPACE}/descriptor.yaml 10"
          }
      }
      
   }
}