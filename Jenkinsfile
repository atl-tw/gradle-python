node('aws_hero_slave_5') {
    checkout scm
    stage('Build') {
        try {
            sh '''
            export GRADLE_OPTS="-Dorg.gradle.daemon=false"
            chmod a+x ./gradlew
            ./gradlew clean build
            '''
        } finally {
            publishHTML( target: [ allowMissing:true, alwaysLinkToLastBuild:false, keepAll:true,
                                   reportDir: 'build/reports/coverage/', reportFiles: 'index.html',
                                   reportName: "Coverage"] )
            publishHTML( target: [ allowMissing:true, alwaysLinkToLastBuild:false, keepAll:true,
                                   reportDir: 'build/reports/dependency-check/', reportFiles: 'report.html',
                                   reportName: "Dependency Check"] )
        }
    }

    stage('Publish') {
            sh '''

            ./gradlew publish
            '''
     }

     stage('Deploy') {
     }
}