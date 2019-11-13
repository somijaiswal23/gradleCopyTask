# Gradle Copy task
Small demo with Gradle as beginner

## Initialize a project

Step 1: cd into project


Step 2: run gradle init script

```dif
F:\gradleCopyTask>gradle init
```

After running the script, it will ask for options:

```dif
Select type of project to generate:
  1: basic
  2: application
  3: library
  4: Gradle plugin
Enter selection (default: basic) [1..4]
```
I will select 1, since its a basic task. After that it will ask for build script DSL. I will proceed with Groovy.
```dif
Select build script DSL:
  1: Groovy
  2: Kotlin
Enter selection (default: Groovy) [1..2]
```
After selecting build script, it will ask for project name:
```dif
Project name (default: gradleCopyTask):       
```
Provide name of the project as you wish.

Below will be the end result:
```dif
> Task :init
Get more help with your project: https://guides.gradle.org/creating-new-gradle-builds

BUILD SUCCESSFUL in 3m 9s
2 actionable tasks: 2 executed
F:\gradleCopyTask>      
```
Create a folder inside your project called src.

```dif
F:\gradleCopyTask>mkdir src

F:\gradleCopyTask>cd src

F:\gradleCopyTask\src>
```
## Add text file
Create a simple text file inside src folder, and write some message.

The folder structure will now look like this:
```dif
├── .gradle
├── .idea
├── src
│   └── hello.txt
├── build.gradle  
├── gradle
│   └── wrapper
│       ├── gradle-wrapper.jar  
│       └── gradle-wrapper.properties  
├── gradlew  
├── gradlew.bat  
└── settings.gradle  
```
## Create Task
Now open build.gradle and write below task. This will be having some comment. You can clear it.

```
task copy(type: Copy, group: "Custom", description: "Copies sources to the dest directory") {
    from "src"
    into "dest"
}
```
Here, group and description can be anything you want. You can even omit them. Now execute your new copy task from cmd:

## Run Task
```
F:\gradleCopyTask\src>cd ..

F:\gradleCopyTask>/gradlew copy


BUILD SUCCESSFUL in 1s
1 actionable task: 1 executed
F:\gradleCopyTask>          

```
Verify that it worked as expected by checking that there is now a file called hello.txt in the dest directory, and that its contents match the contents of the same one in the src directory.
