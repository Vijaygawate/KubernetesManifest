node {
    def app

    stage('Clone repository') {
      

        checkout scm
    }

     stage('Push the changed deployment file to Git'){
            steps {
                script{
                    sh """
                    git config --global user.name "Vijay Gawate"
                    git config --global user.email "vijaygawate79@gmail.com"
                    git add deployment.yml
                    git commit -m 'Updated the deployment file' """
                    withCredentials([usernamePassword(credentialsId: 'github', passwordVariable: 'pass', usernameVariable: 'user')]) {
                        sh "git push http://$user:$pass@github.com/KubernetesManifest.git:main"
                    }
                }
            }
        }
    }
}
