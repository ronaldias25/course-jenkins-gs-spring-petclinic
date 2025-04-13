// scripted pipeline
pipelines {
   agent any
   stages {
       stage("build") {
           steps {
              bat ".\\mvnw.cmd package"
           }
       }
       stage("capture") {
           steps {
               archiveArtifacts '**/target/*.jar'
                  jacoco()
                  junit '**/target/surefire-reports/TEST*.xml'
           }
       }
   }
}
