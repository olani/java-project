node('linux'){
    stage('Test'){
        git 'https://github.com/olani/java-project.git'
        sh 'ant -f test.xml -v'
    }
    stage('Build'){
        sh 'ant -f build.xml -v'
    }

    stage('Deploy'){
        sh 'aws s3 cp ./dist/rectangle-*.jar s3://seis665-hw10/'
    }

    stage('Report'){
        withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'e54241ba-509d-4f4d-a9d0-8a11aea36098', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
           sh 'aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins' 
        }
    }
    
}
