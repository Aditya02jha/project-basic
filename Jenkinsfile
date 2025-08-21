pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Aditya02jha/project-basic.git'
            }
        }

        stage('Deploy') {
            steps {
                bat '''
                if exist "C:\\deployment\\my-website" (
                    rd /S /Q "C:\\inetpub\\my-website"
                )
                mkdir "C:\\inetpub\\my-website"
                xcopy /E /I /Y * "C:\\inetpub\\my-website\\"
                '''
            }
        }
    }
}
