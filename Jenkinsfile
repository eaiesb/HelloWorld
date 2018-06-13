#!/usr/bin/groovy
pipeline {
agent any
options {
disableConcurrentBuilds()
}
stages {
  
stage("buildsrc") {
steps { buildsrc() }
}

stage("Buildimg") {
steps { buildApp() }
}
}
}
// steps
def buildsrc() {
dir ('.' ) {
mvn clean install
mv target/helloworld-1.0.0-SNAPSHOT.zip helloworld.zip
}
}
def buildApp() {
dir ('' ) {
def appImage = docker.build("eaiesbhub/mulehelloworld:${BUILD_NUMBER}")
}
}
