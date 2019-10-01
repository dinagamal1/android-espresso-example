pipeline {
    agent {
       label 'emulator'
          }
    stages {
        stage('Build') {
            steps {
               sh 'gradle build'
             sh 'sudo chown dina:dina /dev/kvm'
                sh 'cd ~'
            }
        }
        stage('Test') {
              steps {
       //  sh 'gradle test'
                            sh 'sudo chown dina:dina /dev/kvm'
                  
                  sh'adb devices'


    } 
        }
        stage('Deliver') {
            steps {
                 
                sh '''
                chmod a+x ./gradlew
                ./gradlew connectedAndroidTest --info
                
                '''

            }
        }
    }
}
