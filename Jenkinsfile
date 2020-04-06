pipeline {
    agent any
    stages {
        stage('SCM Checkout') {
            steps {
                echo 'SCM..'
            }
        }
        stage('Build & Test') {
            steps {
                echo 'Building..'
            }
        }
        stage('Build Tests') {
            parallel {
                stage('Test On Build_Files to Test') {
                    steps {
                        echo "Downloading..."
                    }
                }
                stage('Download Build_Files') {
                    steps {
                        echo "Testing.."
                    }
                }
            }
        }
        stage('Publish to Artifactory') {
            steps {
                echo 'Publishing....'
            }
        }
        stage('Deploy to Development') {
            steps {
                echo 'Deploying..'
            }
        }
        stage('Development Tests') {
            parallel {
                stage('Test On Development Code') {
                    steps {
                        echo "Testing.."
                    }
                }
                stage('Download Development Code') {
                    steps {
                        echo "Downloading.."
                    }
                }
            }
        }
        stage('Deploy to QA') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('QA Tests') {
            parallel {
                stage('Test On QA Code') {
                    steps {
                        echo "Testing.."
                    }
                }
                stage('Download QA Code') {
                    steps {
                        echo "Downloading.."
                    }
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Production Tests') {
            parallel {
                stage('Test On Production Code') {
                    steps {
                        echo "Testing.."
                    }
                }
                stage('Download Production Code') {
                    steps {
                        echo "Downloading.."
                    }
                }
            }
        }
    }    
}
