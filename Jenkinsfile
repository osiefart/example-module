


void executeModuleScripts(String operation) {

          def allModules = ['module1', 'module2', 'module3', 'module4', 'module11']

          allModules.each { module ->
              String action = "${operation}:${module}"

              echo("---- ${action.toUpperCase()} ----")
              String command = "echo ${action} "

            // here is the trick
            script {
              stage(module) {
                bat(command)
              }
            }
          }

}



pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
               echo 'This is a minimal pipeline.'
            }
        }
               stage('Dynamic Part') {
                      steps {
                        executeModuleScripts('build') // local method, see at the end of this script
                      }
                    }

    }
}