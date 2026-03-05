---
title: "Kotlin Project Directory Structure"
date: 2026-03-05
draft: true
slug: "kotlin-project-directory-structure"
layout: post
---


To make it easier to understand the setup of a repository for
Kotlin/Multiplatform and how it is supposed to be somewhat standardized
for the Angelos Project™ organization, there is now a layout to follow
for each new repository being introduced to the project. Each repository
has the ability to add sometimes necessary subprojects to the Gradle 
[multi-project layout](https://docs.gradle.org/current/userguide/multi_project_builds.html). Here, only the standard `:library` subproject is 
introduced. The goal is to normalize every repository to a standard that
may be updated simultaneously based on [syncing](https://kotlinlang.org/docs/multiplatform/multiplatform-compatibility-guide.html) with newer versions of Kotlin
and keep up with their sync and standards with a minimum of deprecation.


```
my-project
 +--.circleci
 |   +--config.yml
 +--gradle
 |   +--wrapper
 |   |   +--gradle-wrapper.properties
 |   +--libs.versions.toml
 +--library
 |   +--src
 |   |   +--commonMain
 |   |   |   +--kotlin
 |   |   |       +--org.angproj.*
 |   |   +--commonTest    
 |   |   |   +--kotlin
 |   |   |       +--org.angproj.*
 |   |   +--jvmTest    
 |   |       +--kotlin
 |   |           +--org.angproj.*
 |   +--build.gradle.kts
 |   +--Module.md
 +--.gitignore
 +--build.gradle.kts
 +--default-detekt-config.yml
 +--gradle.properties
 +--gradlew
 +--gradlew.bat
 +--LICENSE
 +--local.properties
 +--README.md
 +--settings.gradle.kts
```

### my-project/.circleci/config.yml
Currently, the CI/CD environment used is the vendor [CircleCi](https://circleci.com/). 
The config.yml is a configuration playbook to build, test and perform other standardized
operations to automate work in the CI/CD cycle.

### my-project/gradle/gradle-wrapper.properties
All Kotlin based projects uses [Gradle](https://docs.gradle.org/current/userguide/gradle_wrapper.html) in its build process and as a standard toolchain.
The strict choice of Gradle version to be used is found in this file, and should be 
synced between all repositories.

### my-project/gradle/libs.versions.toml
[TOML](https://toml.io/en/) is a type of configuration file format that is supported by Kotlin. This 
is the go to file to find out what libraries and versions of such that is used.
The purpose is to have all this information synchronized between repositories.
It is here you find Java version, Kotlin version, and other versions used.

### my-project/library
This is the standard subproject to be used for the main code a project library. It is key
that absolutely the major part of the code goes into the `commonMain` build target. Likewise
all unittests should go in the `commonTest` test target. The use of Mockito for mocking is
currently only available for Kotlin/Jvm, which is in the `jvmTest` target.

### my-project/library/build.gradle.kts
This is the most important buildscript, all important configuration goes into this file, including version number and group.

### my-project/library/Module.md
This file is related to Kotlin dokka documentation. More will be said later.

### my-project/build.gradle.kts
This file has some shared basic configuration for the whole Gradle multi-project layout.
Note that all plugins are set to `false`, so that they don't activate except in subprojects.

### my-project/default-detekt-config.yml
This is a configuration file that is related to [Codacy](https://www.codacy.com/login),
a tool for code quality checking. Unnecessary documentation checking is disabled for unittest
targets, because it doesn't offer any value for the users implementing the library in their project.

### my-project/gradle.properties
This is the standard gradle properties file. Some settings related to Kotlin and Gradle is set here.
Do not change it, it is supposed to be in sync with the organization standard.

### my-project/gradlew(.bat)
This is the standard CLI entry script. Use `./gradlew clean build allTests` to build and test a library.

### my-project/LICENSE
The license file should be a MIT open source license.

### my-project/local.properties
Never ever check in this file with Git, instead make sure it is included in `.gitignore`. 
Used for android SDK and maybe something more in the future.

### my-project/README.md
The usual README file describing the use and other characteristics.

### my-project/settings.gradle.kts
Contains information on Maven repositories, overall project name, and the declarations
of subproject.