pipeline {
    agent any
    environment{
      GOOGLE_APPLICATION_CREDENTIALS = "/var/lib/jenkins/workspace/android-pipeline/app/android-code-new-d608a52fc088.json"
    }
    

      stages {
          stage('build') {
              steps {
               
                   sh "./gradlew clean build bundleRelease assembleRelease" 
              
              }
          
          }
          stage('Archive Files') {
              steps{
              echo 'Archiving APKs...'
              archiveArtifacts '**/*.apk,**/*.aab'
              
              }
          }
           stage ('Distribute') {
               steps{
              withEnv(environment) {
                  sh "./gradlew assembleRelease appDistributionUploadRelease"
              }
               
          }
           }
           
      }
}
