node {
        stage('Checkout') {
        // Cloning Repo
           git 'https://github.com/vaibhavjain882/emsdockerhub.git'
        }    
        
        stage('SonarQube analysis') {
    // requires SonarQube Scanner 2.8+
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv('Sonar_Server_5.6.6') {
      sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectName=Groovy-Test -Dsonar.projectVersion=1.0 -Dsonar.projectKey=Groovy-Project-Key -Dsonar.sources=."
    }
  }
}
        
        stage('build') {
        // Building Code
           sh 'mvn clean install package'
        }
        
        
        stage('Archive Artefact') {
            // Archive Artefact after build
            archive excludes: '', includes: 'target/*.war'
            
        }
        
        
} 
