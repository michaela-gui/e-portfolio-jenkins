pipeline {
  agent any
  stages {
    stage('build git files') {
      steps {
        build(job: 'GitIntegration', propagate: true)
      }
    }

    stage('print file') {
      steps {
        echo 'check memememeee'
      }
    }

    stage('send positive mail') {
      parallel {
        stage('send positive mail') {
          steps {
            mail(subject: 'jenkins test e-portfolio', body: 'Guten Tag, das ist eine nachricht von jenkins. Git-Files wurden alle korrekt ausgeführt.')
          }
        }

        stage('send negative mail') {
          steps {
            mail(subject: 'jenkins test e-portfolio', body: 'Guten tag, das ist eine nachricht von jenkins. Git-Files wurden nicht korrekt gebaut.')
          }
        }

      }
    }

    stage('tell git') {
      steps {
        git 'https://github.com/michaela-gui/e-portfolio-jenkins.git'
      }
    }

  }
}