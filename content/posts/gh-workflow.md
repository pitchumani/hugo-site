---
date: '2025-01-07T22:32:27+05:30'
title: 'Understanding Continuous Integration and GitHub Workflow Actions'
tags:
  - GitHub Workflow Actions
  - Continuous Integration
  - CI
---

When you write a program, you typically build and test it in a specific environment. For small projects or multiple programs, you might automate these build and test steps using scripts or tools like Makefiles. Makefiles are particularly useful because they only rebuild the files that have changed, making the process more efficient.

Once you've made changes to your project, the next step is to validate those changes. This means you need to have test inputs and expected outputs ready so you can run tests to ensure your changes work as expected and don't break any existing functionality.

Validation should happen before you integrate your changes into the main project. In an automated development system, your project's source code is usually stored in a version control system like Git. Changes are submitted as pull requests (PRs), which are requests to merge changes from one branch into the main branch. Whenever a pull request is created, validation tests should run automatically to check if the changes are good to go.

This process of regularly merging changes into a project is known as Continuous Integration (CI).

On GitHub, Workflow Actions provide a platform for Continuous Integration and Continuous Deployment (CI/CD). This means you can automate the building, testing, and deployment of your projects, making your development process more efficient and reliable.

**Creating a workflow action in GitHub**
1. In your GitHub repository, navigate to .github/workflows directory, if the directory doesn't exist, create it.
2. Inside this directory, create new file with a .yml extension
3. Define the workflow

   - Example: c-cpp.yml
```
name: C/C++ CI

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - name: Install gtest manually
      run: sudo apt-get install libgtest-dev
    - uses: actions/checkout@v4
    - name: build and run tests for c++ programs
      working-directory: cpp
      run: make test
```
4. Customize the workflow as per project requirement
5. Commit and Push the workflow
   - GitHub actions will automatically detect the workflow file and start running defined actions on the specified events (push and pull request in the above example).

