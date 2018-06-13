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
dir ('' ) {
mvn install
}
}
def buildApp() {
dir ('' ) {
def appImage = docker.build("eaiesbhub/mulehelloworld:${BUILD_NUMBER}")
}
}
