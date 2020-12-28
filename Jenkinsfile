node {
    stage('git download'){
		git credentialsId: 'github', url: 'https://github.com/dots24/dot_webapp.git'
    }
    stage('clean') {	
         sh 'mvn clean'    
    }
    stage ('Code Scan')
    {
      sh 'mvn sonar:sonar \
  -Dsonar.host.url=http://34.123.123.129:9000 \
  -Dsonar.login=1232b642b1cefdb7c8e6a91908383dcbe696af20'
    }
    stage('compile') {
        sh 'mvn compile'
    }
	stage('package') {
		sh 'mvn package'
        
    }
		stage('deploy') {
		sh 'mvn deploy'
        
    }
}
