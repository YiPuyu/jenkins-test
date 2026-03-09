pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo '拉取代码...'
                git 'https://github.com/YiPuyu/jenkins-test.git'
            }
        }

        stage('Run Tests') {
            steps {
                echo '运行测试...'
                sh 'python3 -m pytest test_sample.py --tb=short'
            }
        }
    }

    post {
        always {
            echo '测试完成'
        }
        success {
            echo '✅ 所有测试通过'
        }
        failure {
            echo '❌ 有测试失败'
        }
    }
}
