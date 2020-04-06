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
        stage('Run Tests') {
            parallel {
                stage('Download Build_Files to Test') {
                    steps {
                        echo "Downloading..."
                    }
                }
                stage('Test On Build_Files') {
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
        stage('Run Tests') {
            parallel {
                stage('Download Development Code') {
                    steps {
                        echo "Downloading.."
                    }
                }
                stage('Test On Development Code') {
                    steps {
                        echo "Testing.."
                    }
                }
            }
        }
        stage('Deploy to QA') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Run Tests') {
            parallel {
                stage('Download On QA Code') {
                    steps {
                        echo "Downloading.."
                    }
                }
                stage('Test On QA Code') {
                    steps {
                        echo "Testing.."
                    }
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Run Tests') {
            parallel {
                stage('Download Production Code') {
                    steps {
                        echo "Downloading.."
                    }
                }
                stage('Test On Production Code') {
                    steps {
                        echo "Testing.."
                    }
                }
            }
        }
    }    
}
