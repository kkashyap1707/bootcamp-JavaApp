#!groovy
pipeline {
    agent any

    environment {
        EMAIL_RECIPIENTS = 'keshav.kashyap@tothenew.com'
    }

      stages {
          stage('Checkout') {
              steps {
                  deleteDir()
                  checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '7bcd6522-500e-42da-bc10-4d0ae79c2067', url: 'git@github.com:kkashyap1707/bootcamp-JavaApp.git']]]
              }
          }
          stage("maven") {
              steps {
                  script {
                      withMaven(maven: "mavenTool")
                              {
                                  sh(script: """mvn clean package""")
                              }
                  }
              }
          }
      }

}