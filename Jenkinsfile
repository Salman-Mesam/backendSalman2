pipeline {
  agent { label "linux" }
  stages {
    stage("build") {
      steps {
        sh """
          docker build -t springboot-docker1 .

        """
      }
    }
    stage("run") {
      steps {
        sh """
          docker run --rm springboot-docker1
        """
      }
    }
  }
}
