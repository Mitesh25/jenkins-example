pipeline {
	agent any
		stages {
			stage ('SCM Checkout') {
				steps {
					git 'https://github.com/Mitesh25/jenkins-example.git'
				}
			}
			stage ('Validate Source Code') {
				steps {
					withMaven(maven: 'My_Maven') {
						sh 'mvn validate'
					}
				}
			}
			stage ('Compile Source Code') {
				steps {
					withMaven(maven: 'My_Maven'){
						sh 'mvn clean compile'
					}
				}
			}
			stage ('Test Source Code') {
				steps {
					withMaven(maven: 'My_Maven'){
						sh 'mvn test'
					}
				}
			}
			
			stage ('Package Source Code') {
				steps {
					withMaven(maven: 'My_Maven') {
						sh 'mvn package'
					}
				}
			}
			stage ('Install Source Code') {
				steps {
					withMaven(maven: 'My_Maven') {
						sh 'mvn install'
					}
				}
			}
			
	}}
