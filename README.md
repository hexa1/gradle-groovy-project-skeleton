A bootstrap of a typical Gradle Groovy Project
==============================================

A starting point for gradle-based Groovy projects.

Includes:

- Groovy plugin
- Application plugin
- Codenarc
- An extensive Codenarc ruleset configuration
- Generated x-platform gradlew scripts
- Groovydoc
- Unit Testing

Useful Commands
===============

- `./gradlew dist` create a stand-alone distributable jar file in the `dist` folder
- `./gradlew test` test everything
- `./gradlew codenarcMain` codenarc only main source files
- `./gradlew codenarcTest` codenarc only test source files
- `./gradlew build` build the whole project
- `gradle wrapper` Regenerate wrapper (graldew, gradlew.bat)

Directory Structure
===================

```
.
├── LICENSE     => Your app License
├── README.md
├── build       => Build directory
│   └── README.md
├── build.gradle => Main Groovy build file
├── codenarc-ruleset.groovy => Ruleset for codenarc
├── codenarcReport.html -> ./build/reports/codenarc/main.html => A symlink to the generated codenarc report (for utility)
├── dist
│   └── README.md    => generated .jar file will go here
├── docs
│   └── README.md   => documentation
├── gradle => assets for gradlew wrapper (application plugin)
│   └── wrapper
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── gradlew   => x-platform gradle bootstrap
├── gradlew.bat => same as above for windows
├── src  => source files go here, namespaced (using folders) according to package
│   └── app
│       └── Main.groovy
├── test => Spock and JUnit (and other) tests go here
└── testReport.html -> ./build/reports/tests/index.html  => a symlink to the generated test report by running ./gradlew test
```

Notes
=====

- Intially, all CodeNarc rules are enabled (except for SystemOutPrint, and Println), making for a very uptight development environment, edit `codenarc-ruleset.groovy` to make it more bearable. But for OCD enabling, it's great :)


TODO
====

- Exclude codenarc for unit tests