# Dockerfile Bug: Missing requirements.txt

This repository demonstrates a common error in Dockerfiles: attempting to copy a file that doesn't exist in the build context.  The original Dockerfile fails to build because `requirements.txt` is not present. The solution demonstrates how to correctly include the necessary file.

## Bug
The original `Dockerfile` attempts to copy `requirements.txt` and install dependencies, but this file is missing, resulting in a build failure.

## Solution
The `Dockerfile_fixed` includes a `requirements.txt` file, demonstrating the correct way to manage dependencies in Docker.

To reproduce the bug:
1. Build the original Dockerfile using `docker build -t my-app .` (it will fail)
2. Build the fixed Dockerfile using `docker build -t my-app-fixed .` (this will succeed)