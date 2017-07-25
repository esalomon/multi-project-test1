# multi-project-test1
This project contains a Grails Application and a Grails Plugin, the application is configured to use the plugin and there is no more. It was created using the Grails 3.2.7 version.

# Creation
Following the Plugins and Multi-Project Builds section at the Grails 3 manual, a Multi-project could be configured following the next commands in a terminal:

```
echo "Creating the root folder..."
mkdir multi-project-test1
cd multi-project-test1

echo "Creating the settings.gradle file..."
echo "include 'myapp', 'myplugin'" >> settings.gradle

echo "Creating the Grails application..."
grails create-app myapp

echo "Creating the Grails plugin..."
grails create-plugin myplugin

echo "Configuring the dependency between the application and the plugin..."
echo "grails { plugins { compile project(':myplugin') } }" >> myapp/build.gradle 

echo "Executing the Grails application..."
cd myapp
grails run-app 
```

Note, sdk is used to handle the Grails versions and the commands were executed using Java 1.7 and Yosemite:

    JVM: 1.8.0_131 (Azul Systems, Inc. 25.131-b11)
    OS:  Mac OS X 10.11.6 x86_64

# Output

The grails run-app` command will execute the application without problem and will display the next output:

```
$ cd myapp
$ grails run-app
| Resolving Dependencies. Please wait...

CONFIGURE SUCCESSFUL

| Running application...
objc[18332]: Class JavaLaunchHelper is implemented in both /Users/esalomon/.sdkman/candidates/java/8u131-zulu/bin/java and /Users/esalomon/.sdkman/candidates/java/8u131-zulu/jre/lib/libinstrument.dylib. One of the two will be used. Which one is undefined.
18:01:26,072 |-INFO in ch.qos.logback.classic.LoggerContext[default] - Found resource [logback.groovy] at [file:/Users/esalomon/grails3tests/multi-project-test1/myapp/grails-app/conf/logback.groovy]
18:01:26,076 |-WARN in ch.qos.logback.classic.LoggerContext[default] - Resource [logback.groovy] occurs multiple times on the classpath.
18:01:26,076 |-WARN in ch.qos.logback.classic.LoggerContext[default] - Resource [logback.groovy] occurs at [file:/Users/esalomon/grails3tests/multi-project-test1/myapp/grails-app/conf/logback.groovy]
18:01:26,076 |-WARN in ch.qos.logback.classic.LoggerContext[default] - Resource [logback.groovy] occurs at [file:/Users/esalomon/grails3tests/multi-project-test1/myplugin/build/resources/main/logback.groovy]
18:01:27,218 |-INFO in ch.qos.logback.classic.gaffer.ConfigurationDelegate@2141a12 - registering conversion word clr with class [org.springframework.boot.logging.logback.ColorConverter]
18:01:27,231 |-INFO in ch.qos.logback.classic.gaffer.ConfigurationDelegate@2141a12 - registering conversion word wex with class [org.springframework.boot.logging.logback.WhitespaceThrowableProxyConverter]
18:01:27,243 |-INFO in ch.qos.logback.classic.gaffer.ConfigurationDelegate@2141a12 - About to instantiate appender of type [ch.qos.logback.core.ConsoleAppender]
18:01:27,246 |-INFO in ch.qos.logback.classic.gaffer.ConfigurationDelegate@2141a12 - Naming appender as [STDOUT]
18:01:27,521 |-INFO in ch.qos.logback.classic.gaffer.ConfigurationDelegate@2141a12 - About to instantiate appender of type [ch.qos.logback.core.FileAppender]
18:01:27,521 |-INFO in ch.qos.logback.classic.gaffer.ConfigurationDelegate@2141a12 - Naming appender as [FULL_STACKTRACE]
18:01:27,524 |-INFO in ch.qos.logback.core.FileAppender[FULL_STACKTRACE] - File property is set to [/Users/esalomon/grails3tests/multi-project-test1/myapp/build/stacktrace.log]
18:01:27,530 |-INFO in ch.qos.logback.classic.gaffer.ConfigurationDelegate@2141a12 - Setting level of logger [StackTrace] to ERROR
18:01:27,537 |-INFO in ch.qos.logback.classic.gaffer.ConfigurationDelegate@2141a12 - Attaching appender named [FULL_STACKTRACE] to Logger[StackTrace]
18:01:27,541 |-INFO in ch.qos.logback.classic.gaffer.ConfigurationDelegate@2141a12 - Setting level of logger [ROOT] to ERROR
18:01:27,541 |-INFO in ch.qos.logback.classic.gaffer.ConfigurationDelegate@2141a12 - Attaching appender named [STDOUT] to Logger[ROOT]
18:01:27,542 |-INFO in ch.qos.logback.classic.gaffer.ConfigurationDelegate@2141a12 - Attaching appender named [FULL_STACKTRACE] to Logger[ROOT]

Grails application running at http://localhost:8080 in environment: development
```
