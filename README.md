# GithubActions
a GitHub Composite Action that does the following:

Takes a Docker image name as a parameter.
Fetches the latest tag number (without suffixes).
Pulls the image onto the runner.
Retags the image for a Nexus repository.
Pushes the image to the Nexus repository.
