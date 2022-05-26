//
// pipeline{
//    agent {
//        node {
//            label 'ansible'
//        }
//    }
//    options{
//      disableConcurrentBuilds()
//      ansiColor('xterm')
//    }
//
//    parameters {
//            string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//            text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
//            booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
//            choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
//            password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
//        }
//
//    environment {
//      DEMO_URL= "google.com"
//      SSH=credentials("SSH")
//    }
//     stages {
//         stage('Test'){
//          environment{
//            DEMO_URL="yahoo.com"
//          }
//           steps {
//             echo 'Hello World'
//             echo DEMO_URL
//             echo SSH
//             sh 'echo -e "\\e[31mHello"'
//           }
//         }
//
//     stage('Test1'){
//               steps {
//                 echo 'Hello World'
//               }
//        }
//     }
// }
//
//

//

// pipeline
// {
//   agent any
//
//   environment {
//      ENV='dev'
//   }
//    stages {
//       stage('high-level1') {
//       when {
//         expression {
//           ENV=='prod'
//         }
//       }
//       stages {
//          stage('One') {
//           steps {
//             sh 'echo one'
//           }
//          }
//          stage('Two') {
//            steps {
//             sh 'echo two'
//           }
//        }
//       }
//      }
//
//    }
// }

pipeline
{
  agent any

  environment {
     ENV='dev'
  }
   stages {
      stage('high-level1') {
         stages {
            parallel {
                stage('One') {
                    steps {
                        sh 'echo one'
                    }
                }
                stage('Two') {
                    steps {
                        sh 'echo two'
                    }
                }
            }
        }
     }

   }
}