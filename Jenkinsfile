pipeline {

    agent any

   stages {

      stage('CleanWorkspace') {
            steps {
                cleanWs()
            }
      }

      stage('Download Juliops jar file') {
          steps {
              sh "cd ${WORKSPACE} && wget https://github.com/kafka-ops/julie/releases/download/v2.1.2/FAT.jar.zip && unzip FAT.jar.zip -d ${WORKSPACE}"
          }
      }
      
      stage('Create topics') {
          steps {
              sh "java -jar --broker 172.30.247.219:9092 --clientConfig ${WORKSPACE}/kafka_config.conf --topology ${WORKSPACE}/descriptor.yaml"
          }
      }
      
   }
}