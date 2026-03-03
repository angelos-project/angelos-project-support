---
title: "Normalizing Angelos Project™ Repositories to One Standard"
date: 2026-03-03
draft: true
slug: "normalizing-angelos-project-repositories-to-one-standard"
description: "The goal is to normalize the coding style, versions and code quality in the different compoments spread out over the different repositories in the Angelos Project™. The reason is to hold everything in sync so it works flawlessly together."
layout: post
---

# Normalizing Angelos Project™ Repositories to One Standard

The project has been developed by one person now for 7 years and
6 month. The first step was to develop a Proof o Concept with the 
basic functionalities in Python for testing a simple server and
client setup. In this period many different integrated components
where tested and primarily fitted out.

About three years was spent on developing concept components for
the Angelos platform, App and server which finished in August 2021.
At the moment God spoke to Kristoffer, the founder/owner of the
project to move on to a new programming language, Kotlin. From there
on it has been a struggle to get all the pieces together but it has
slowly progressed. The biggest hurdle was to be able to ship packages
with Sonatype Maven Central.

Also more than 4 years has been spent developing the underlying
technology to to Angelos. The Kotlin developers mainly focus on
delivering code for Android but also text based servers like Ktor.
Therefore it has also been necessary to build a server/client code
infrustructure to be able to do what is necessary for the Angelos
platform concept.

Those four years that has been spent on developing underlying 
infrastructure of code has been focusing on reinventing the wheel
of Java piping and streaming. The goal is to deliver the same 
classes, interfaces, methods and functions to Kotlin/Multiplatform (KMP)
with a minimum of outside dependencies. KMP is built on multiple
build targets that spans both over platforms, processor architectures,
operating systems and different large IT vendors such as Apple, Google
and diverse others. Here the projects aims for a streamlined codebase
with minimum import of arbitrary 3rd party packages. Everything is 
aimed to be put in the Kotlin/Common build target. Only a minimum
necessary should be placed in other specialized build targets.
Something that Jetbrains haven't aimed for. Their goal seems to have
been to include third party libraries for each build target putting
all interfaces and abstract in the common build target.

Because the development has been solitary for over 7 years, it is 
now time to open up the Angelos Project™ to contributors. Thereby
also a focus on aiming for shipping some production code and a few
first components. In this case the codebase need to be unified in 
standards such as:
- What should the repository structure look like
- What versions of the toolchain should be used, e.g. Java 17, Gradle 8.1.1, Kotlin 1.9.25 and procedure for synchronized updates
- What should the unit testing be structured like
- And last how can a CI/CD development cycle be formed and put in place for collaboration with contributors and alike

Therefore effort will be put into setting up a functional project 
organization that is functional for contributors and other persons.
Also normalization means to bring in each repository one at a time
in a normalized state to always work together. That means that development
circumstances needs to be type of standardized. It may take some 
time and effort but time and energy will be placed there.

Welcome aboard!<br>
Wished for you<br>
by Kristoffer Paulsson<br>
Project founder/author/owner