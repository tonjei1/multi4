pipeline{
  agent any
  stages{
    stage('version-control'){
      steps{
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'tonjei1', url: 'https://github.com/tonjei1/multi4.git']]])
      }
    }
    stage('parallel-job1'){
      parallel{
        stage('sub-job1'){
          steps{
            echo 'action01'
          }
        }
        stage('sub-job2'){
          steps{
            echo 'action2'
          }
        }
      }
    }
    stage('codebuild'){
      steps{
        sh 'cat /etc/passwd'
      }
    }
  }
}

