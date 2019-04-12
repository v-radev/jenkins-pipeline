pipeline {
    agent any
    options { timeout(time: 5) }
    parameters {
        booleanParam(name: 'DEBUG_BUILD', defaultValue: true, description: 'Is it the debug build?')
    }
    stages {
        stage('Example') {
            environment { NAME = 'Batman' }
            when {
                expression {
                    return params.DEBUG_BUILD
                }
            }
            steps {
                echo "Hello from $NAME"
                script {
                    def browsers = ['chrome', 'firefox']
                    for (int i = 0; i < browsers.size(); ++i) {
                        echo "Testing the ${browsers[i]} browser."
                    }
                }
            }
        }
    }
}
