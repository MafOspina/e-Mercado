pipeline {
    agent any

    stages {
        stage('Call another Jenkinsfile') {
            steps {
                script {
                    def params = [
                        string(name: 'PARAM1', value: 'value1'),
                        string(name: 'PARAM2', value: 'value2')
                    ]

                    /*def jenkinsfile = load 'https://github.com/MafOspina/DevOps/main/Jenkinsfile'
                    jenkinsfile.execute(params)*/

                    def jenkinsfile = sh(script: "curl -s https://github.com/MafOspina/DevOps/main/Jenkinsfile", returnStdout: true)
                    jenkinsfile = new GroovyShell().parse(jenkinsfile)
                    jenkinsfile.execute(params)
                }
            }
        }
    }
}