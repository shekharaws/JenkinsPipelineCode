   pipeline {
    agent any
    stages {
        
        stage('pull code from github repo') {
            steps {
                git credentialsId: 'shekhar', url: 'git@github.com:shekharaws/boxfuse-sample-java-war-hello.git'
            }
        }
        
        stage('triggerring aws codebuild project') {
            steps {
                awsCodeBuild artifactEncryptionDisabledOverride: '', artifactLocationOverride: '', artifactNameOverride: '', artifactNamespaceOverride: '', artifactPackagingOverride: '', artifactPathOverride: '', artifactTypeOverride: '', awsAccessKey: '', awsSecretKey: '', buildSpecFile: '', buildTimeoutOverride: '', cacheLocationOverride: '', cacheModesOverride: '', cacheTypeOverride: '', certificateOverride: '', cloudWatchLogsGroupNameOverride: '', cloudWatchLogsStatusOverride: '', cloudWatchLogsStreamNameOverride: '', computeTypeOverride: '', credentialsId: 'awscodebuild', credentialsType: 'jenkins', cwlStreamingDisabled: '', downloadArtifacts: 'false', downloadArtifactsRelativePath: '', envParameters: '', envVariables: '', environmentTypeOverride: '', exceptionFailureMode: '', gitCloneDepthOverride: '', imageOverride: '', insecureSslOverride: '', localSourcePath: '', overrideArtifactName: '', privilegedModeOverride: '', projectName: 'project-uday', proxyHost: '', proxyPort: '', region: 'ap-south-1', reportBuildStatusOverride: '', s3LogsEncryptionDisabledOverride: '', s3LogsLocationOverride: '', s3LogsStatusOverride: '', secondaryArtifactsOverride: '', secondarySourcesOverride: '', secondarySourcesVersionOverride: '', serviceRoleOverride: '', sourceControlType: 'jenkins', sourceLocationOverride: '', sourceTypeOverride: '', sourceVersion: '', sseAlgorithm: '', workspaceExcludes: '', workspaceIncludes: '', workspaceSubdir: ''
            }
        }
    }
    post {
        success {
             //sh 'echo "This Build is succesfull." | mailx -vvv -s "Build Status" shekharg1497@gmail.com'
             sh 'echo "Hi, Build is successful. Please check the below logs for the same." | mailx -vvv -s "Build logs for ${JOB_NAME}" -a /var/lib/jenkins/jobs/${JOB_NAME}/builds/${BUILD_NUMBER}/log "shekharg1497@gmail.com"'
             //emailext attachLog: true, body: 'This is My test mail', subject: 'Test Mail', to: 'shekharg1497@gmail.com'
             }
        failure {
            sh 'echo "Hi, Build is Failure. Please check the below logs for the same." | mailx -vvv -s "Build logs for ${JOB_NAME}" -a /var/lib/jenkins/jobs/${JOB_NAME}/builds/${BUILD_NUMBER}/log "shekharg1497@gmail.com"'
             //sh 'echo "This Build is Failed." | mailx -vvv -s "Build Status" shekharg1497@gmail.com'
             }
        }
}
