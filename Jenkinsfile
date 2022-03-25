def version
def modifiedFiles
def skipBuild
node{
      stage("compile"){
            if (fileExists('simpleproject')){
                  sh 'rm -r simpleproject'
            }
            git credentialsId: 'FaizalGit', url: 'https://github.com/faizalgit/simpleproject'
            sh 'git clone https://github.com/faizalgit/simpleproject'
	    sh 'mvn package'
	    nexusArtifactUploader artifacts: [[artifactId: 'simpleproject', classifier: '', file: 'target/simpleproject.war', type: 'war']], credentialsId: 'nexus-upload', groupId: 'com.simpleproject', nexusUrl: '104.196.30.112:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-nexus-repo', version: 'v1'

      }
        
}
