pipeline {

    agent any

   stages {

<<<<<<< HEAD:Jenkinsfile
=======
    stages {
>>>>>>> develop:Jenkinsfileverify
      stage('CleanWorkspace') {
            steps {
                cleanWs()
            }
<<<<<<< HEAD:Jenkinsfile
      }

      stage('Download Juliops jar file') {
=======
            
      stage('verify-replication-factor') {
>>>>>>> develop:Jenkinsfileverify
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