#!/usr/bin/env groovy

pipeline {
    agent any
    parameters {
        password(
                name: "NEMESIS_DOCS_SSH_NEMESIS_PASSWORD",
                defaultValue: "AxugXiP0iJ3akteYzDbFZ6so2lGe4B",
                description: "The key to upload nemesis documentation.",
        )
        password(
                name: "NEMESIS_REPOSITORY_HTTP_PASSWORD",
                defaultValue: "8Rw1e0eLcCyrBwAh3ZsiILzWBCOWtyC8",
                description: "The key to access nemesis maven artifactory repository."
        )
        password(
                name: "NEMESIS_JENKINS_GITHUB_PASSWORD",
                defaultValue: "YmUxZTdlNjc0YzY4YjRlZDlmNTQ4ZGE4",
                description: "The key to access nemesis github repository."
        )
        string(
                name: "mvn",
                defaultValue: "/opt/bitnami/apache-maven-3.5.0/bin/mvn",
                description: "Path to maven executable."
        )
        string(
                name: "MAVEN_OPTS",
                defaultValue: "-Xms2G -Xmx3G -Xss128M -XX:+CMSClassUnloadingEnabled",
                description: "The maven opts environment variable."
        )
        string(
                name: "releaseVersion",
                defaultValue: "2.0.1.RELEASE",
                description: "Specify the release version")
        string(
                name: "developmentVersion",
                defaultValue: "2.0.2.BUILD-SNAPSHOT",
                description: "Specify the next development version after this release.")
        booleanParam(
                name: "dryRun",
                defaultValue: true,
                description: "")
    }
    stages {
        stage('Release BOM') {
            steps {
                release job: 'nemesis-bom-master',
                        parameters: [
                                password(name: 'NEMESIS_DOCS_SSH_NEMESIS_PASSWORD', value: NEMESIS_DOCS_SSH_NEMESIS_PASSWORD),
                                password(name: 'NEMESIS_REPOSITORY_HTTP_PASSWORD', value: NEMESIS_REPOSITORY_HTTP_PASSWORD),
                                password(name: 'NEMESIS_JENKINS_GITHUB_PASSWORD', value: NEMESIS_JENKINS_GITHUB_PASSWORD),
                                string(name: 'mvn', value: mvn),
                                string(name: 'MAVEN_OPTS', value: MAVEN_OPTS),
                                string(name: 'releaseVersion', value: releaseVersion),
                                string(name: 'developmentVersion', value: developmentVersion),
                                booleanParam(name: 'dryRun', value: Boolean.valueOf(dryRun))
                        ]
            }
        }

        stage('Release Platform') {

            steps {
                release job: 'nemesis-platform-master',
                        parameters: [
                                password(name: 'NEMESIS_DOCS_SSH_NEMESIS_PASSWORD', value: NEMESIS_DOCS_SSH_NEMESIS_PASSWORD),
                                password(name: 'NEMESIS_REPOSITORY_HTTP_PASSWORD', value: NEMESIS_REPOSITORY_HTTP_PASSWORD),
                                password(name: 'NEMESIS_JENKINS_GITHUB_PASSWORD', value: NEMESIS_JENKINS_GITHUB_PASSWORD),
                                string(name: 'mvn', value: mvn),
                                string(name: 'MAVEN_OPTS', value: MAVEN_OPTS),
                                string(name: 'releaseVersion', value: releaseVersion),
                                string(name: 'developmentVersion', value: developmentVersion),
                                booleanParam(name: 'dryRun', value: Boolean.valueOf(dryRun))
                        ]
            }
        }

        stage('Release Archetype') {
            steps {
                release job: 'nemesis-archetype-master',
                        parameters: [
                                password(name: 'NEMESIS_DOCS_SSH_NEMESIS_PASSWORD', value: NEMESIS_DOCS_SSH_NEMESIS_PASSWORD),
                                password(name: 'NEMESIS_REPOSITORY_HTTP_PASSWORD', value: NEMESIS_REPOSITORY_HTTP_PASSWORD),
                                password(name: 'NEMESIS_JENKINS_GITHUB_PASSWORD', value: NEMESIS_JENKINS_GITHUB_PASSWORD),
                                string(name: 'mvn', value: mvn),
                                string(name: 'MAVEN_OPTS', value: MAVEN_OPTS),
                                string(name: 'releaseVersion', value: releaseVersion),
                                string(name: 'developmentVersion', value: developmentVersion),
                                booleanParam(name: 'dryRun', value: Boolean.valueOf(dryRun))
                        ]
            }
        }

        stage('Release Console') {
            steps {
                release job: 'nemesis-console-master',
                        parameters: [
                                password(name: 'NEMESIS_DOCS_SSH_NEMESIS_PASSWORD', value: NEMESIS_DOCS_SSH_NEMESIS_PASSWORD),
                                password(name: 'NEMESIS_REPOSITORY_HTTP_PASSWORD', value: NEMESIS_REPOSITORY_HTTP_PASSWORD),
                                password(name: 'NEMESIS_JENKINS_GITHUB_PASSWORD', value: NEMESIS_JENKINS_GITHUB_PASSWORD),
                                string(name: 'mvn', value: mvn),
                                string(name: 'MAVEN_OPTS', value: MAVEN_OPTS),
                                string(name: 'releaseVersion', value: releaseVersion),
                                string(name: 'developmentVersion', value: developmentVersion),
                                booleanParam(name: 'dryRun', value: Boolean.valueOf(dryRun))
                        ]
            }
        }

    }

}
