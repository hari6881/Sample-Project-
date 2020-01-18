pipeline {
          agent any
                  stage('one') {
                               steps {
                                      echo 'hi, this is hari from Dhrm'
                                     }
                    }
                   stage('two') {
                                  steps {
                                         input('do you want to proceed?')
                                         }
                    }
                    stage('three') {
                                when {
                                      not {
                                           branch "master"
                                           }
                                     }
                                     steps {
                                            echo "hello"
                                            }
                                        }
                    stage('four') {
                                   parallel {
                                             stage ('Unit testing') {
                                                                    steps {
                                                                            echo "Runnig the unit test....."
                                                                            }
                                              }
                                              stage('Integration test") {
                                                                 agent {
                                                                        docker {
                                                                                reuseNode false image 'ubuntu'
                                                                      }
                                                               }
                                                               steps {
                                                                      echo 'Running the integration test.....'
                                                                      }
                                                      }
                                              }
}
}
}
}
