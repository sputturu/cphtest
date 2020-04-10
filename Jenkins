pipeline {
    agent any
    stages {
        stage('SCM Checkout') {
            steps {
                echo 'SCM..'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Build Tests') {
            parallel {
                stage('CH_CPH_AccessManagement_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_UserProfile_CD') {
                    steps {
                        echo "Building.."
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
                stage('CH_CPH_AccessManagement_CD') {
                    steps {
                        echo "Testing.."
                    }
                }
                stage('CH_CPH_UserProfile_CD') {
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
                stage('CH_CPH_AccessManagement_CD') {
                    steps {
                        echo "Testing.."
                    }
                }
                stage('CH_CPH_UserProfile_CD') {
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
                stage('CH_CPH_AccessManagement_CD') {
                    steps {
                        echo "Testing.."
                    }
                }
                stage('CH_CPH_UserProfile_CD') {
                    steps {
                        echo "Downloading.."
                    }
                }
            }
        }
    }    
}
