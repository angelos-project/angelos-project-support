---
title: "Kotlin Project Directory Structure"
date: 2026-03-05
draft: true
slug: "kotlin-project-directory-structure"
description: ""
layout: page
---

```
my-project
 +--.circleci
 |   +-- config.yml
 +--gradle
 |   +--wrapper
 |   |   +--gradle-wrapper.properties
 |   +--libs.versions.toml
 +--library
 |   +--src
 |       +--commonMain
 |       |   +--kotlin
 |       |       +--org.angproj.*
 |       +--commonTest    
 |       |   +--kotlin
 |       |       +--org.angproj.*
 |       +--jvmTest    
 |       |   +--kotlin
 |       |       +--org.angproj.*
 |       +--build.gradle.kts
 |       +--Module.md
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