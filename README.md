# GithubActions
a GitHub Composite Action that does the following:

Takes a Docker image name as a parameter.
Fetches the latest tag number (without suffixes).
Pulls the image onto the runner.
Retags the image for a Nexus repository.
Pushes the image to the Nexus repository.

name: "Use Custom Action - Push Docker Image to Nexus"

on:
  push:
    branches:
      - main

jobs:
  push-to-nexus:
    runs-on: ubuntu-latest
    steps:
      - name: "Checkout Code"
        uses: actions/checkout@v4

      - name: "Use Custom Action"
        uses: your-github-username/github-actions-nexus-push@main
        with:
          image_name: "your-dockerhub-image"
          nexus_registry: "nexus.example.com"
          nexus_repo: "docker-hosted"
          nexus_username: ${{ secrets.NEXUS_USERNAME }}
          nexus_password: ${{ secrets.NEXUS_PASSWORD }}

