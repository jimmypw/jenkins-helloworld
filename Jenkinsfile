podTemplate (containers: [
    containerTemplate(
        name: 'rust', 
        image: 'rust:bullseye', 
        command: 'sleep', 
        args: '1d'
        )
  ]){
    node(POD_LABEL) {
        container('rust') {
            checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/jimmypw/jenkins-helloworld.git']])
            stage('QC') {
                /* TODO: Quality Control */
            }
            stage('test') {
                sh 'cargo test'
            }
            stage('build') {
                sh 'cargo build'
                sh 'cargo build --release'
            }
        }
    }
}
