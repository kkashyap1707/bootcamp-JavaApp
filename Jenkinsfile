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
                  checkout([$class: 'GitSCM', branches: [[name: "*/${params.BRANCH}"]], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'git-credentials', url: 'git@github.com:allyo-org/QA_JobReqAutomation.git']]])
              }
          }
          /*stage("maven") {
              steps {
                  script {
                      withMaven(maven: "mavenTool")
                              {
                                  sh(script: """mvn clean package""")
                              }
                  }
              }
          }*/
      }

}