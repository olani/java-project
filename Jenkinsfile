node('linux'){
    stage('Build'){
        git 'https://github.com/rclc/java-project.git'
        sh 'ant -f build.xml -v'
    }
}
