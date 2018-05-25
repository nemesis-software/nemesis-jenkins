#!/usr/bin/env groovy

pipeline {
    agent any
    parameters {
        string(
                name: "releaseVersion",
                defaultValue: "",
                description: "Specify the release version")
        string(
                name: "developmentVersion",
                defaultValue: "",
                description: "Specify the next development version after this release.")
        booleanParam(
                name: "dryRun",
                defaultValue: false,
                description: "")
    }

    stages {
        stage('Release BOM') {
            release(
                    job: "nemesis-bom-master",
                    parameters {
                        string(
                                name: "releaseVersion",
                                value: "${params.releaseVersion}")
                        string(
                                name: "developmentVersion",
                                value: "${params.developmentVersion}")
                        booleanParam(
                                name: "dryRun",
                                value: "${params.dryRun}")
                    }
            )
        }

        stage('Release Platform') {
            release(
                    job: "nemesis-bom-master",
                    parameters {
                        string(
                                name: "releaseVersion",
                                value: "${params.releaseVersion}")
                        string(
                                name: "developmentVersion",
                                value: "${params.developmentVersion}")
                        booleanParam(
                                name: "dryRun",
                                value: "${params.dryRun}")
                    }
            )
        }

        stage('Release Archetype') {
            release(
                    job: "nemesis-bom-master",
                    parameters {
                        string(
                                name: "releaseVersion",
                                value: "${params.releaseVersion}")
                        string(
                                name: "developmentVersion",
                                value: "${params.developmentVersion}")
                        booleanParam(
                                name: "dryRun",
                                value: "${params.dryRun}")
                    }
            )
        }

        stage('Release Console') {
            release(
                    job: "nemesis-bom-master",
                    parameters {
                        string(
                                name: "releaseVersion",
                                value: "${params.releaseVersion}")
                        string(
                                name: "developmentVersion",
                                value: "${params.developmentVersion}")
                        booleanParam(
                                name: "dryRun",
                                value: "${params.dryRun}")
                    }
            )
        }

    }

}
