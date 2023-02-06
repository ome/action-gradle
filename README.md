# action-gradle

This action is a [composite action](https://docs.github.com/en/actions/creating-actions/creating-a-composite-action)
that will install:
 - Java (default 11)
 - Gradle (default 6.8.3)

Both Java and Gradle version can be passed as a parameter.
If an empty string is passed for the Gradle parameter, the latest version (whatever that is) of Gradle will be installed.

 To use the action in a workflow:

 ```
on: [push]

jobs:
  install_job:
    runs-on: ubuntu-20.04
    name: A job to install Gradle and Java
    steps:
      - uses: actions/checkout@v3
      - name: Install Java and Gradle
        uses: ome/action-gradle@v2
 ```

If you wish to change the Java version, for example use Java 1.8

 ```
on: [push]

jobs:
  install_job:
    runs-on: ubuntu-20.04
    name: A job to install Gradle and Java
    steps:
      - uses: actions/checkout@v3
      - name: Install Java and Gradle
        uses: ome/action-gradle@v2
        with:
          java-version: 8
 ```

 To change the Gradle version, use the parameter ``gradle-version``.
