# genexus-devops-integration

> **⚠️ Archived:** This repository is archived and no longer actively maintained.

This repository provides MSBuild scripts and Azure DevOps pipeline templates to automate the build and deployment of GeneXus Knowledge Bases (KBs) through Azure DevOps CI/CD pipelines.

For full documentation, see [Continuous integration with Azure DevOps](https://docs.genexus.com/en/wiki?52078,Table+of+contents%3AContinuous+integration+with+Azure+DevOps,) on the GeneXus wiki.

## Contents

- **`AzureCICD.msbuild`** — MSBuild script that wraps GeneXus build tasks. Exposes the following targets:
  - `CreateOrUpdateKB` — creates a new KB or updates it from GeneXus Server
  - `Build` — compiles the KB and generates the deployable output
  - `RunTestSuite` — executes GeneXus automated tests and exports results in JUnit format

- **`ContinuousBuildKb.yml`** — Azure DevOps pipeline definition that orchestrates the full CI/CD workflow:
  1. Checks out or updates the KB from GeneXus Server
  2. Builds and deploys to Azure if there are pending updates
  3. Pushes the generated source files to a Git repository

## Setup

Copy `AzureCICD.msbuild` to the root of your GeneXus installation directory and configure the pipeline variables in `ContinuousBuildKb.yml` according to your environment.

## Trademarks

This project references third-party products and services.
All trademarks are the property of their respective owners. Use of these
names does not imply endorsement or affiliation with GeneXus S.A.

- **Microsoft Azure** and **Azure DevOps** are trademarks of Microsoft Corporation.

## License

Licensed under the [Apache License 2.0](LICENSE).
Copyright 2022 GeneXus S.A.
