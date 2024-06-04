node('built-in') {
    stage('ContinuousDownload') {
        git 'https://github.com/intelliqittrainings/maven.git'
    }

    stage('ContinuousBuild') {
        sh 'mvn package'
    }

    stage('ContinuousDeployment') {
        sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline5/webapp/target/webapp.war ubuntu@172.31.39.29:/var/lib/tomcat9/webapps/tester.war'
    }

    stage('ContinuousTesting') {
        git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
        sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline5/testing.jar'
    }
    
    stage('ContinuousDelivery') {
        sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline5/webapp/target/webapp.war ubuntu@172.31.39.242:/var/lib/tomcat9/webapps/tester.war'
    }

}
