stage('Deploy') {
    steps {
        sh '''
        pm2 delete nodejs-app || true
        pm2 start app.js --name nodejs-app
        pm2 save
        '''
    }
}
