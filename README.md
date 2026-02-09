# example-java

[![view-action-graph](https://img.shields.io/github/actions/workflow/status/actionforge/example-java/workflow.yml?label=View%20Action%20Graph)](https://app.actionforge.dev/github/actionforge/example-java/main/.github/workflows/graphs/build.act)

A simple Hello World app in Java, built using an [Actionforge](https://actionforge.dev) graph as the CI/CD pipeline.

## Run

```bash
javac HelloWorld.java
jar cfe HelloWorld.jar HelloWorld HelloWorld.class
java -jar HelloWorld.jar
```

## Graph

The build pipeline is defined as an Actionforge graph in [`.github/workflows/graphs/build.act`](.github/workflows/graphs/build.act):

```
checkout -> run (compile & package jar) -> upload-artifact (HelloWorld.jar)
```

It runs on every push to `main`, on pull requests, and on manual dispatch.
