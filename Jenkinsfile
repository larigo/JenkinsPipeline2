pipeline {
    agent any
    parameters {
        string(name: 'username', defaultValue: 'u1', description: 'Current Username')
        string(name: 'local_server', defaultValue: '192.168.186.1', description: 'My Computer')
        string(name: 'EmailAdress', defaultValue: 'ig.larionov@gmail.com', description: 'Notifications Email Address')
    }
    stages {
            stage('Step-1: Clean Maven ') {
                steps {
                    dir ('my-app') {
                        sh "mvn clean"
                    }
                }
            }
            stage('Step-2: Compiling And Creating The Job') {
                steps{
                    dir ('my-app') {
                        sh "mvn package"
                    }
                }   
            }
            stage('Step-3: Executing the jar file') {
                steps{
                    dir ('my-app') {
                        sh "java -jar ./target/my-app-1.0-SNAPSHOT.jar"
                    }
                }
            }
            stage ('Step-4: Run'){
			    steps{
                    dir ('my-app') {
                         sh "java -cp ./target/classes ru.apache_maven.App"
                    }
                }
            }

	}
}
