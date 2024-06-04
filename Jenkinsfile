node('Built-in'){
    stage('ContinuousDownload') {
        try {
            git 'https://github.com/intelliqittrainings/maven.git'
        }
        catch(Exception e1){
            mail bcc: '', body: 'unable to download the code', cc: '', from: '', replyTo: '', subject: 'Download has failed', to: 'git.admin@gmail.com'
            exit()
        }
    }
    stage('ContinuousBuild') {
        try {
            sh 'mvn package'
        }
        catch(Exception e2){
            mail bcc: '', body: 'unable to built the code', cc: '', from: '', replyTo: '', subject: 'Build has failed', to: 'Dev.admin@gmail.com'
            exit()
        }
    }
}
