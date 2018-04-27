pipeline {
  agent any
  stages {
    stage('init') {
      parallel {
        stage('init') {
          steps {
            echo '123'
          }
        }
        stage('init1') {
          steps {
            echo '21121'
          }
        }
        stage('testsleep') {
          steps {
            sleep(time: 5, unit: 'MINUTES')
          }
        }
      }
    }
    stage('git') {
      steps {
        git(url: 'https://gitee.com/jamesz2011/jmeter_jenkins_mvn.git', branch: 'master', changelog: true)
      }
    }
    stage('autoTest') {
      steps {
        echo 'autotest'
      }
    }
    stage('emailsend') {
      steps {
        mail(subject: 'test_report', body: '123321', charset: 'UTF-8', from: 'jamesz2011@126.com', to: 'jamesz2011@126.com')
      }
    }
  }
}