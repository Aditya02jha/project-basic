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
                if [ -d "/var/www/project-basic" ]; then
                    rm -rf "/var/www/project-basic"
                fi
                mkdir -p "/var/www/project-basic"
                cp -r * "/var/www/project-basic"
                '''
            }
        }
    }
}
