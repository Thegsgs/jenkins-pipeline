pipeline {
  agent any
    stages {
        stage('build') {
            steps {
                  sh('''
                    git config user.email "jenkins@gmail.com"
                    git config user.name "Jenkins"
                    git config push.default simple
                    git checkout -b test-branch
                    echo "echo HELLO TEST WORLD!!!" > test.sh
                    sh test.sh
                    git add .
                    git commit -m "initial commit on test branch"
                    git push -u origin test-branch
                    ''')
                }

            }
        }
    }
  post {
    always {
      cleanWs()
    }
  }