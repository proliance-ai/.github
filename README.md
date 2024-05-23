# GitHub Starter Workflows

Welcome to the `.github` repository for our organization! This repository contains predefined GitHub Actions starter workflows that can be used as templates for new projects.
These templates help standardize our CI/CD processes across all repositories within the organization.

## Table of Contents

- [Introduction](#introduction)
- [Usage](#usage)
    - [How to Use a Template](#how-to-use-a-template)
    - [Using Starter Workflows via GitHub UI](#using-starter-workflows-via-github-ui)
- [Available Templates](#available-templates)
    - [Template 1: Reusable Docker Build for Backend Applications](#template-1-reusable-docker-build-for-backend-application)
    - [Template 2: Reusable Docker Build for Frontend Applications](#template-2-reusable-docker-build-for-frontend-applications)
    - [Template 3: Complete CI for Backend Applications](#template-3-complete-ci-for-backend-applications)
    - [Template 4: Complete CI for Frontend Applications](#template-4-complete-ci-for-frontend-applications)
    - [Template 5: Delete Container Packages](#template-5-delete-container-packages)
    - [Template 6: Reusable New Relic Frontend Source Maps Uploading](#template-6-reusable-new-relic-frontend-source-maps-uploading)

## Introduction

This repository contains a collection of reusable GitHub Actions workflows that can be used as starting points for setting up CI/CD pipelines in your new projects. By using these templates, you can ensure consistency and best practices across all projects within our organization.
Each workflow is located in the [workflow-templates](./workflow-templates) directory and have `.yml` extension.
The respective `.properties.json` files you may find under the same directory is used to store the properties of the workflows to display them in the GitHub UI.
The <u>suffix</u> of the concrete workflow file's name matters.
<u>The suffix</u> tells us what type of project this workflow is intended for. For example, the `-frontend.yml` workflow is intended to be used for frontend projects.

[README.md](./profile/README.md) file in the `profile` directory contains the organization's profile information.

## Usage

### How to Use a Template

1. **Create a New Repository:**
   When creating a new repository, navigate to the `.github` repository and find the desired workflow template.

2. **Copy the Workflow File:**
   Copy the YAML file of the desired workflow template from this repository.

3. **Add the Workflow to Your Repository:**
   Paste the copied YAML file into the `.github/workflows` directory of your new repository.

4. **Customize the Workflow:**
   Modify the copied workflow to suit the specific needs of your project. Make sure to update any placeholders or specific configurations required.
   There might be hardcoded values in the workflow that you need to replace with your own values such as project name, environment variables, etc.

### Using Starter Workflows via GitHub UI

1. **Navigate to Your New Repository:**
   Go to the repository where you want to set up the workflow.

2. **Access the Actions Tab:**
   Click on the "Actions" tab at the top of the repository page.

3. **Select "New Workflow":**
   Click on the "New workflow" button to view the available starter workflows.

4. **Choose a Starter Workflow:**
   Browse through the starter workflows listed under the "Workflows created by your organization" section. Select the desired workflow template.

> **Note:** The starter workflows currently are only available for new **public** repositories.
> If you want to use the starter workflows in a private repository, you can follow the steps mentioned in the [How to Use a Template](#how-to-use-a-template) section.
> Basically, usage of starter workflows for a private repository is available for enterprise license customers only.
> Refer to the [GitHub documentation](https://docs.github.com/en/actions/using-workflows/creating-starter-workflows-for-your-organization#creating-a-starter-workflow) for more information.

## Available Templates

### Template 1: Reusable Docker Build for Backend Applications

The file name is [reusable-docker-build-backend.yml](./workflow-templates/reusable-docker-build-backend.yml).
It is a [reusable workflow](https://docs.github.com/en/actions/using-workflows/reusing-workflows) for building multiplatform container images.
`The reusable Docker Build for Backend Applications` workflow is designed to build Docker (container) images for backend applications. It supports building images for multiple platforms and includes distributed caching for improved build times.
> **Note:** This workflow is intended to be used in conjunction with the `Complete CI for Backend Applications` workflow.

### Template 2: Reusable Docker Build for Frontend Applications

The file name is [reusable-docker-build-frontend.yml](./workflow-templates/reusable-docker-build-frontend.yml).
It is a [reusable workflow](https://docs.github.com/en/actions/using-workflows/reusing-workflows) for building multiplatform container images.
`The reusable Docker Build for Frontend Applications` workflow is designed to build Docker (container) images for frontend applications. It supports building images for multiple platforms and includes distributed caching for improved build times.
> **Note:** This workflow is intended to be used in conjunction with the `Complete CI for Frontend Applications` workflow.

### Template 3: Complete CI for Backend Applications

The file name is [complete-ci-backend.yml](./workflow-templates/complete-ci-backend.yml).
`The Complete CI for Backend Applications` workflow is designed to provide a comprehensive CI pipeline for backend applications. It includes building the application with Maven, running unit tests, displaying test coverage, building Docker images for multiple platforms.

### Template 4: Complete CI for Frontend Applications

The file name is [complete-ci-frontend.yml](./workflow-templates/complete-ci-frontend.yml).
`The Complete CI for Frontend Applications` workflow is designed to provide a comprehensive CI pipeline for frontend applications. It includes building the application with Yarn, building Docker images for multiple platforms, testing assembled container, and uploading source maps to New Relic.

### Template 5: Delete Container Packages

The file name is [delete-container-packages.yml](./workflow-templates/delete-container-packages.yml).
`The Delete Container Packages` workflow is designed to clean up old, unused, or untagged container images from the GitHub Container Registry. It runs on a schedule and can be manually triggered only from the `default` branch as well.
> **Note:** For better handling of the cleanup process, the workflow should be customized to meet the specific needs of the project.

### Template 6: Reusable New Relic Frontend Source Maps Uploading

The file name is [reusable-nr-sourcemaps-upload-frontend.yml](./workflow-templates/reusable-nr-sourcemaps-upload-frontend.yml).
`Reusable New Relic Frontend Source Maps Uploading` workflow is designed to upload source maps to New Relic for frontend applications.
> **Note:** This workflow is intended to be used in conjunction with the `Complete CI for Frontend Applications` workflow.
> Current implementation of this workflow is a native-based: installing -> building -> uploading source maps.
> In the future, we hate to change the implementation to a container-based approach for better performance.

For more detailed information about each workflow, please refer to the respective workflow file in the [workflow-templates](./workflow-templates) directory.
