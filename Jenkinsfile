pipeline {
    agent {label "mob"}
    stages {
        stage ("Git clone") {
            steps {
                git branch: 'master', credentialsId: 'github', url: 'https://github.com/tejesh555/mahalogin'
            }
        }
        stage ("Build") {
            steps {
                script {
                    sh "mvn clean install"
                }
            }
        }
        stage ("test") {
            steps {
                script {
                    sh "echo 'test cases'"
                }
            }
        }
/*        stage ("Publish") {
            steps {
                    rtUpload (
                        serverId: 'myjfrog',
                        spec: '''{
                              "files": [
                                {
                                  "pattern": "target/*.war",
                                  "target": "mahalogin/"
                                }
                             ]
                        } '''
                    )
            }
        }  */
        stage ("deploy") {
            steps {
                script {
                    echo "ansible adhoc-command"
                }
            }
        }
    }
}
