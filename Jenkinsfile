node {
    stage('git download'){
		git credentialsId: 'gitlab', url: 'http://35.223.128.153/root/kspro.git'
    }
    stage('clean') {	
         sh 'mvn clean'    
    }
    stage ('Code Scan')
    {
      sh 'mvn sonar:sonar \
  -Dsonar.host.url=http://35.224.98.36:9000 \
  -Dsonar.login=000b43bf0dceb307f16f6f9fb598868a13dc5f8e'
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