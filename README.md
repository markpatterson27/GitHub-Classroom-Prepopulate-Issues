# GitHub Classroom - Prepopulate Issues

Workflow file that prepopulates an assignment repository with issues when a student accepts the assignment.

Requirements:

- The workflow file is intended to be used with [GitHub Classroom](https://classroom.github.com) assignments.
- Feedback pull request needs to be enabled for the assignment.

**Note:** the workflow makes use of the [Project API](https://docs.github.com/en/rest/reference/projects), which is currently in preview stage and subject to change. It is possible that by the time you read this, the API has changed and the workflow is broken.

## How to use

1. Copy the `.github/workflows/prepopulate-issues.yml` file to your assignment repository's workflow directory.
2. For each issue you want to create, add a text file to the `.github/STARTING_ISSUES` directory. The filename of each file will become the issue title and the contents of the file will be the issue's body.

## What the workflow does

- The workflow runs when the `feedback` branch is created.
- The workflow creates a Project called "Assignment Tasks" and a column called "To Do".
- The workflow then iterates through the files in the `.github/STARTING_ISSUES` directory, creating an issue per file and adding that issue to the "To Do" column in the project.
