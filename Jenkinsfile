node {
        stage('Checkout') {
        // Cloning Repo
           git 'https://github.com/vaibhavjain882/emsdockerhub.git'
        }    
        
        stage('build') {
        // Building Code
           sh 'mvn clean install package'
        }
        
        stage('Archive Artefact') {
            // Archive Artefact after build
            archive excludes: 'target/*.war', includes: ''
            
        }
} 
