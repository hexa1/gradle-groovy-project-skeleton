### GoGo Groovy Gradle [![Build Status](https://travis-ci.org/hexa1/gogo-groovy-gradle.svg)](https://travis-ci.org/hexa1/gogo-groovy-gradle)

A starting point for gradle-based Groovy projects, a bootstrap of a typical Gradle Groovy Project

- Groovy 2.4.5
- Gradle 2.9

Includes:

- Groovy plugin
- Application plugin
- Pitest plugin
- Codenarc
- Asciidoctor with sample docs
- Asciidoctor PDF, HTML5, and EPUB backends
- An extensive Codenarc ruleset configuration
- Generated x-platform gradlew scripts
- Groovydoc
- Unit Testing support
- Sample Application main class and package
- Sample Spock Test case
- Sample JUnit Test case
- Example of a FatJar task: create a distributable jar with all deps
- Example of a provided config: define compile-time deps without them being in the distributable jar: useful for building groovy libs and excluding Groovy! (or Slf4j)
- Gradle daemon
- S3 maven and ivy repos

Useful Commands
===============

- `$ ./app` Run the application in development as standalone (emulates distribution)
- `$ ./gradle wrapper` Regenerate wrapper (graldew, gradlew.bat)
- `$ ./gradlew dist` create a stand-alone distributable jar file in the `dist` folder
- `$ ./gradlew test` test everything or `./test.sh`
- `$ ./gradlew codenarcMain` codenarc only main source files
- `$ ./gradlew codenarcTest` codenarc only test source files
- `$ ./gradlew groovydoc` generate documentation using Groovydoc 2 (pretty!)
- `$ ./gradlew build` build the whole project or `./build.sh`
- `$ ./gradlew asciidoctor` Generate ascii doctor docs
- `$ ./gradlew pitest` Run pitest

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
├── libs            => extra jars go here
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
└── testReport.html -> ./build/reports/tests/index.html  => a symlink to the generated test 
report by running ./gradlew test
└── app => run the app with arguments in development mode
```

### Notes

- Intially, all CodeNarc rules are enabled (except for SystemOutPrint, and Println), making for a very uptight development environment, edit `codenarc-ruleset.groovy` to make it more bearable. But for OCD enabling, it's great :)
- To exclude compile dependency from fat jar, mark it as `provided` instead of `compile` in dependencies

### Useful Resources

- http://www.mkyong.com/logging/logback-xml-example/

### TODO

- As in lazybones generator (gradle-quickstart), add code coverage/quality tools, break apart gradle config, use a rule-based codenarc config (for granular excludes)
- Break up gradle file organization, like in lazybones griffon generator
- Exclude codenarc for unit tests
- include code generation, standard header for files, etc...
- Increment semver build number
