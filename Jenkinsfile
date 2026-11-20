pipeline {
            agent any

            stages {
                stage('Build & Check') {
                    steps {
                        echo 'Checking repository files...'
                        sh 'ls -la'
                    }
                }

                stage('Test') {
                    steps {
                        echo 'Verifying index.html has a valid heading...'
                        sh 'grep -q "<h1>" index.html'
                    }
                }

                stage('Deploy to Nginx') {
                    steps {
                        echo 'Deploying website to live Nginx server...'
                        sh 'cp -f index.html /var/www/html/index.html'
                        sh 'chmod 644 /var/www/html/index.html'
                    }
                }
            }
        }
