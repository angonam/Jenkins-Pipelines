## Table of contents:
1. Jenkins Pipeline.
2. Using Jenkinsfile.
3. Multi Branch pipelines.
4. Pipeline development tools.
5. Pipeline Syntax.

## Jenkins Pipeline :

Jenkins Pipeline is a suite of plugins which supports implementing and integrating continuous delivery pipelines into Jenkins. Pipeline provides an extensible set of tools for modeling simple-to-complex delivery pipelines "as code" via the Pipeline DSL.

Scripted Pipeline is written in Groovy.

A basic Pipeline can be created in either of the following ways:

By entering a script directly in the Jenkins web UI.
By creating a Jenkinsfile which can be checked into a project’s source control repository.

To create a basic Pipeline in the Jenkins web UI, follow these steps:

```sh
a) Click "New Item" on Jenkins home page.
b) Enter a name for your Pipeline, select "Pipeline" and click OK.
c) In the Script text area, enter a Pipeline and click Save.
d) Click "Build Now" to run the Pipeline.
e) Click (1#) under "Build History" and then click "Console Output" to see the full output from the Pipeline.
```

## Using Jenkinsfile:

Pipeline provides an extensible set of tools for modeling simple-to-complex delivery pipelines "as code" via the Jenkinsfile.

```sh
Jenkinsfile (Declarative Pipeline)
pipeline {
agent any

stages {
stage('Build') {
steps {
sh 'make'
}
}
stage('Test'){
steps {
sh 'make check'
junit 'reports/**/*.xml'
}
}
stage('Deploy') {
steps {
sh 'make publish'
}
}
}
}
```

```sh
"agent" indicates that Jenkins should allocate an executor and workspace for this part of the Pipeline.
"stage" describes a stage of this Pipeline.
"steps" describes the steps to be run in this stage
"sh" executes the given shell command
"junit" is a Pipeline step provided by the JUnit plugin for aggregating test reports.
```
## Multi-Branch pipelines:
The Multibranch Pipeline project type enables you to implement different Jenkinsfiles for different branches of the same project. In a Multibranch Pipeline project, Jenkins automatically discovers, manages and executes Pipelines for branches which contain a Jenkinsfile in source control.
This eliminates the need for manual Pipeline creation and management.

To create a Multi-Branch pipeline:
```sh
a) Click "New Item" on Jenkins home page.
b) Enter a name for your Pipeline, select "Multi-Branch" Pipeline and click "OK".
c) Add a "Branch Source" (for example, Git) and enter the location of the repository.
d) Save the "Multibranch Pipeline" project

```

## Pipeline development tools:
Jenkins Pipeline includes built-in documentation and the Snippet Generator which are key resources when developing Pipelines. They provide detailed help and information that is customized to the currently installed version of Jenkins and related plugins.
Also , view the references below for more information
[Blue ocean pipeline editor](https://jenkins.io/doc/book/blueocean/pipeline-editor/)
[Command-line Pipeline Linter](https://en.wikipedia.org/wiki/Lint_(software))

# Pipeline Syntax:
A pipeline is a Groovy script that tells Jenkins what to do when your Pipeline is run. You do not need to know much general Groovy to use Pipeline - relevant bits of syntax are introduced as needed.

[Pipeline Syntax](https://github.com/jenkinsci/pipeline-plugin/blob/master/TUTORIAL.md)
