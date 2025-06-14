podTemplate (containers: [
    containerTemplate(
        name: 'rust', 
        image: 'rust:bullseye', 
        command: 'sleep', 
        args: '1d'
        )
  ]){
    node(POD_LABEL) {
        stage('Build') {
            container('rust') {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/jimmypw/jenkins-helloworld.git']])
                stage('Dev') {
                    sh 'cargo build'
                }
            }

        }
    }
}
