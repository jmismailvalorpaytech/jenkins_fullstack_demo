/* groovylint-disable-next-line CompileStatic */
pipeline {
    agent any
    tools { nodejs 'Node16.15.0' }
    stages {
        stage('Test npm') {
            steps {
                sh '''
              npm --version
        '''
            }
        }
        stage('Build') {
            steps {
                sh ''' 
                    cd client
                    npm install 
                '''
                // sh 'npm install'
                // sh 'npm run build'
            }
        }
        stage('Deploy') {
            steps {
                // sh 'sudo -S  rm -rf /var/jenkins_fullstack_demo/'
                // sh "cd  ${WORKSPACE} && mkdir build"

                sh ''' 
                   cd ${WORKSPACE}/client/dist && ls
                   sudo cp -r * /var/www/jenkins_fullstack_demo/
                ''' 
                // sh "cd ${WORKSPACE}/dist && ls"
                // sh "cp * /var/www/jenkins_fullstack_demo/"
                // sh 'pm2 delete 0'
                // sh 'cd /var/www && mkdir jmismail'
            // sh 'cd /var/www/jenkins-react-app/ && ls'
            }
        }
    }
}