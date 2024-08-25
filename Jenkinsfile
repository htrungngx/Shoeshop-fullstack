pipeline {
    agent {
      label 'dev-server'
    }
    environment {
        appUser = "shoeshop"
        appName = "shoe-ShoppingCart"
        appVersion = "0.0.1-SNAPSHOT"
        appType = "jar"
        processName = "${appName}-${appVersion}.${appType}"
        folderDeploy = "datas/shoeshop"
        buildScript = "mvn clean install -DskipTests=true"
    }
    stages {
        stage('Info') {
            steps {
                sh(script: """ whoami;pwd;ls -la """, label: "first stage")
            }
        }
        stage('Build') {
            steps {
                sh(script: """ ${buildScript} """, label: "build with maven")
            }
        }
    }
}
