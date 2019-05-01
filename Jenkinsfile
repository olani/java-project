node('linux'){
    stage('Test'){
        sh 'ant -f test.xml -v'
    }
    stage('Build'){
        sh 'ant -f build.xml -v'
    }
}
