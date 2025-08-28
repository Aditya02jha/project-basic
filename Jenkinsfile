// pipeline {
//     agent any

//     stages {
//         stage('Checkout') {
//             steps {
//                 git branch: 'master', url: 'https://github.com/Aditya02jha/project-basic.git'
//             }
//         }

//         stage('Deploy') {
//             steps {
//                 bat '''
//                 if exist "C:\\deployment\\my-website" (
//                     rd /S /Q "C:\\deployment\\my-website"
//                 )
//                 mkdir "C:\\deployment\\my-website"
//                 xcopy /E /I /Y * "C:\\deployment\\my-website\\"
//                 '''
//             }
//         }
//     }
// }

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
                sh '''
                if [ -d "/deployment/my-website" ]; then
                    rm -rf "/deployment/my-website"
                fi
                mkdir -p "/deployment/my-website"
                cp -r * "/deployment/my-website/"
                '''
            }
        }
    }
}
