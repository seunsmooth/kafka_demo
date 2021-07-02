pipeline {

    agent any

   stages {
      stage('verify-replication-factor') {
          steps {
              sh "verify-replication-factor.sh ${env.WORKSPACE}/descriptor.yaml 3"
          }
      }
      stage('verify-num-of-partitions') {
          steps {
              sh "verify-num-of-partitions.sh ${env.WORKSPACE}/descriptor.yaml 12"
          }
      }
      stage('test env') {
          steps {
              sh "echo ${descriptor.yaml} & ls -ltr"
          }
      }
   }
}