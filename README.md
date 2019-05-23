Python-Gradle Example
=====================

Purpose
-------

This is a template project for creating a Python AWS Lambda deployable package.

Prerequisites
--------------

Java 8+ installed
Python 3.7 installed
pip installed 

The following environment variables set:


### Windows


Maybe place the etc/pip.ini file in %APPDATA%\pip

### Unix


Build
-----

Run ```gradlew build``` in the project folder

Publish
-------

Run ```gradle publish``` in the project folder to generate an SHA256 hash of the zip, and push to S3 for deployment.


Outputs
-------

1. build/deploy -- Folder containing the deployable directory
1. build/project.zip -- AWS deployable zip
1. build/project.sha -- SHA256 hash of the zip for AWS.
1. build/reports/dependency-check -- Folder containing dependency analysis
1. build/reports/coverage -- Folder with test coverage report

PyCharm Setup
-------------

PyCharm will not import from Gradle directly, so you need to do a couple of things.

1. Under Settings-> Project Python Interpreter, select the one in the .gradle/python directory
1. Under Settings-> Project Structure, set...
   * /build : excluded
   * /src/main/python : sources
   * /src/test/python : sources