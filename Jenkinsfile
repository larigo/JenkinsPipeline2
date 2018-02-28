pipeline {
    agent any

    stages {
            stage('stage-1: Clean Maven ') {
                steps {
                    dir ('my-app') {
                        bat "mvn clean"
					}
                }
            }
            stage('stage-2: Compiling And Creating The Job') {
                steps{
                    dir ('my-app') {
                        bat "mvn package"
					}
                }
            }
            stage('stage-3: Executing the jar file') {
                steps{
                    dir ('my-app') {
                        bat "java -jar ./target/my-app-1.0-SNAPbatOT.jar"
					}
                }
            }
            stage ('stage-4: Run'){
			    steps{
                    dir ('my-app') {
                         bat "java -cp ./target/classes com.mycompany.app.App"
					}
                }
            }
	}
}
