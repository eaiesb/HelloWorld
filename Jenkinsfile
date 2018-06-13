#!/usr/bin/groovy
pipeline {
    environment {
        JAVA_HOME = /app/ciplatform/jdk1.8.0_101
    }
agent any
options {
disableConcurrentBuilds()
}
stages {
  
stage("buildsrc") {
steps { buildsrc() }
}

stage('renamiing the target zip file') {
    steps {
         bash '''#!/bin/bash
                 mv target/helloworld-1.0.0-SNAPSHOT.zip helloworld.zip 
         '''
    }
}  
  
stage("Buildimg") {
steps { buildApp() }
}
}
}
// steps
def buildsrc() {
dir ('.' ) {
    sh '/app/ciplatform/apache-maven-3.3.9/bin/mvn clean install'
}
}
def buildApp() {
dir ('' ) {
def appImage = docker.build("eaiesbhub/mulehelloworld:${BUILD_NUMBER}")
}
}
