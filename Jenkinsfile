pipeline {
    agent any
    stages {
        stage('Ejemplo') {
            steps {
                script {
                    // Configura los parámetros que deseas enviar
                    def parametros = [
                        [$class: 'StringParameterValue', name: 'parametro1', value: 'valor1'],
                        [$class: 'StringParameterValue', name: 'parametro2', value: 'valor2']
                    ]
                    
                    // Llama al paso de construcción del repositorio B y envía los parámetros
                    step([$class: 'ParameterizedRemoteTrigger', remoteJenkinsName: 'https://github.com/MafOspina/DevOps.git', job: 'job1', propagate: true, parameters: parametros])
                }
            }
        }
    }
}


