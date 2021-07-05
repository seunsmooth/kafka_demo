pipeline {

    agent any

   stages {
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
       
      stage('Download Juliosp file') {

          steps {
              sh "cd ${WORKSPACE} && wget https://github.com/kafka-ops/julie/releases/download/v2.1.2/FAT.jar.zip && unzip FAT.jar.zip -d ${WORKSPACE}"
          }
      }
      stage('Create topics') {
          steps {
              sh "java -jar --broker localhost:9092 --clientConfig ${WORKSPACE}/kafka_config.conf --topology ${WORKSPACE}/descriptor.yaml"
          }
      }
      
      
   }
}

      
      
      
   }
   }
