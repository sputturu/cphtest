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
                stage('CH_CPH_Appointment_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_Connection_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_Consent_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_FHIR_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_Invitation_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_Location_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_MedPlan_Activity_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_Notification_Device_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_Observation_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_Plan_ActivityDefinition_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_Questionnaire_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_RequestStudy_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_RequestSubject_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_StudySite_CD') {
                    steps {
                        echo "Building.."
                    }
                }
                stage('CH_CPH_Task_CD') {
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
