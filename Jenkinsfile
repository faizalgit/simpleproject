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
      }
        
}
