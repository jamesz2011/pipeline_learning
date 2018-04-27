pipeline {
  agent any
  stages {
    stage('init') {
      parallel {
        stage('init') {
          agent any
          steps {
            echo '123'
          }
        }
        stage('cleanup') {
          steps {
            cleanWs(deleteDirs: true)
          }
        }
        stage('testsleep') {
          steps {
            sleep(time: 5, unit: 'MINUTES')
            sleep 3
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
      agent any
      steps {
        mail(subject: 'test_report_666', body: '123321', charset: 'UTF-8', from: 'jamesz2011@126.com', to: 'jamesz2011@126.com,214513972@qq.com')
      }
    }
  }
}