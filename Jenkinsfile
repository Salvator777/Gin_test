pipeline {
    agent any

    stages {
        stage('pull code') {
            steps {
                git branch: 'main', credentialsId: 'github-user-pwd', url: 'https://github.com/Salvator777/Gin_test.git'
            }
        }
        stage('build project') {
            steps {
                sh '''echo "开始构建"
                    echo "构建完成"'''
            }
        }
        stage('deploy project') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: '192.168.32.10', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'echo "success"', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: 'gin-test', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}
