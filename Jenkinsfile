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
                stage('Dev') {
                    sh 'cargo build'
                }
            }

        }
    }
}
