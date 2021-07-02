pipeline {

    agent any

   stages {
      stage('verify-replication-factor') {
          steps {
              sh 'verify-replication-factor.sh ${descriptor.yaml} 3'
          }
      }
      stage('verify-num-of-partitions') {
          steps {
              sh 'verify-num-of-partitions.sh ${descriptor.yaml} 12'
          }
      }
   
   }
}