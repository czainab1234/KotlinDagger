pipeline {
    agent any
    

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
           
      }
}
