pipeline {
    agent any 
    parameters { 
         string(defaultValue: "1.0.0.0", description: 'Image version ', name: 'imageversion')
               string(defaultValue: "containername", description: 'Container Name ', name: 'containername')
    
    }

stages{
        stage ('DOcker build image using Dockerfile'){
         steps {
            sh 'docker build -t node-sample:${imageversion} . ' 
}
        }
    
        stage('Docker Images') { 
            steps {
                sh 'docker images'
            }
        }
    stage('list of exisitng continaer ') { 
            steps {
              sh 'docker ps -a'
    }
}
     stage('Docker Remove containers') { 
            steps {
                sh 'docker rm -f $(docker ps -aq)'
            }
        }
      stage('docker Containers') { 
            steps {
                sh 'docker run -d -p 3000:3000 --name ${containername} node-sample:${imageversion} '
            }
        }
stage('Delpoy nodejs application') { 
            steps {
              sh 'docker ps -a'
    }
}
    
}
    // post{
     //   always{
      //      mail to: "raob6730@gmail.com",
       //     subject: "Test Email",
        //    body: "Test"
        //}
    //}

}
