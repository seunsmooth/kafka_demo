pipeline {

    agent any

   stages {
      stage('Download Juliops jar file') {
          steps {
              sh "curl -O https://github.com/kafka-ops/julie/releases/download/v2.1.2/FAT.jar.zip && unzip FAT.jar.zip ."
          }
      }
      
      stage('Create topics') {
          steps {
              sh "java -jar --broker 82.23.130.14:9092 --clientConfig ${WORKSPACE}/kafka_config.conf --topology ${WORKSPACE}/descriptor.yaml"
          }
      }
      
   }
}