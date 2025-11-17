pipeline {

   agent any

   tools{
      maven 'maven-3.9'
   }

   stages {
      stage('Clone') {
         steps {
			script {
				echo "📦 Récupération du code source..."
				checkout scm
			}			 
         }
      }
	  stage('Compile'){
         steps{
         	sh "mvn compile"
         }
      }
      stage('Test'){
         steps{
        	sh "mvn test"
         }
      }
      
      stage('Build'){
         steps{
            sh "mvn -B -DskipTests clean install"
         }
      }
      
//       stage ('SonarQube analysis') {
//         steps {
//            withSonarQubeEnv(installationName: 'My local Sonar', credentialsId: '1150527b-92b9-4ebe-a1e0-6f7adef21174') {
//               sh 'mvn clean sonar:sonar -Dsonar.login=$Login -Dsonar.password=$Password'
//            }
//         }
//      } 
   }
}
