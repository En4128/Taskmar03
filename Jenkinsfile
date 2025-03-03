pipeline {
    agent any
    stages {
        stage('Git') {
            steps {
                git branch: 'main', url: 'https://github.com/En4128/Taskmar03.git'
            }
        }
        stage('Build WAR File') {
            steps {
                sh 'mkdir -p webapp/WEB-INF'
                sh 'cp index.html webapp/'
                sh 'echo "<web-app><display-name>Sample Web App</display-name></web-app>" > webapp/WEB-INF/web.xml'
                sh 'jar -cvf sample.war -C webapp/ .'
            }
        }
        stage('Archive WAR') {
            steps {
                archiveArtifacts artifacts: 'sample.war', fingerprint: true
            }
        }
    }
}
