# ci-experiments

|Coverity Scan|Build Status|
|:-:|:-:|
|[![Coverity Scan](https://scan.coverity.com/projects/13021/badge.svg?flat=1)](https://scan.coverity.com/projects/zebastian-ci-experiments)|Linux / OSX: [![Build Status](https://travis-ci.org/zebastian/ci-experiments.svg?branch=master)](https://travis-ci.org/zebastian/ci-experiments), Windows: [![Build status](https://ci.appveyor.com/api/projects/status/cb0woxak6orvynsl?svg=true)](https://ci.appveyor.com/project/zebastian/ci-experiments)|

Analyse verschiedener Cloud Testing Anbieter im Rahmen der Seminararbeit des Fachs Software Engineering

## Projekt
Das eigentliche Projekt ist eine ausführbare Dummy Datei in /src/main.c
Diese wird durch die Cmake Build Konfiguration in CMakeLists.txt beschrieben.

## Testing Provider

### Travis
In der Datei *.travis.yml* findet sich die Konfiguration des Projekts zum Bauen auf OSX und Linux.

### Appveyor
In der Datei *.appveyor.yml* findet sich die Konfiguration des Projekts zum Bauen auf Windows.
