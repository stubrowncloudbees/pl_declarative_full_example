pipeline {
  agent none
  stages {
    stage('Images') {
      parallel {
        stage('Building Image 1') {
          agent {
            kubernetes {
              label 'pl_scripted_docker_dind'
              containerTemplate {
                name 'maven'
                image 'maven:3.3.9-jdk-8-alpine'
                ttyEnabled true
                command 'cat'
              }

            }

          }
          steps {
            echo 'building image'
          }
        }
        stage('Building Image 2 ') {
          steps {
            echo 'building image 2'
          }
        }
      }
    }
    stage('Compilation') {
      parallel {
        stage('Compiling 1') {
          steps {
            echo 'compiling 1'
          }
        }
        stage('Compiling 2') {
          steps {
            echo 'Compiling 2'
          }
        }
      }
    }
    stage('Package') {
      parallel {
        stage('Package 1') {
          steps {
            echo 'Package 1'
          }
        }
        stage('Package 2') {
          steps {
            echo 'Package 2'
          }
        }
        stage('Package 3') {
          steps {
            echo 'Package 3'
          }
        }
      }
    }
  }
}