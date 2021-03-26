## Docker: All the Cool Things

* Installing Docker: https://docs.docker.com/engine/install/
  * ```
    # Windows installation steps.
    # 1. Download and run this .exe:
    https://desktop.docker.com/win/stable/Docker%20Desktop%20Installer.exe
    ```
  * ```
    # Linux installation steps.
    # TODO: Add installation steps for Linux.
    ```

* Pull a Docker image:
  * ```
    # Downloads the latest LTS Ubuntu Docker image from DockerHub.
    docker pull ubuntu:20.04
    ```
- Create a Docker container:
  * ```
    # Creates a new Docker container named 'hoohacks2021-first-container' running ubuntu v20.04.
    # (--interactive == give us an interactive shell; --tty == connect our stdin + stdout)
    docker run --name hoohacks2021-first-container --interactive --tty ubuntu:20.04 bash
    ```
- Remove a Docker container:
  * ```
    # Removes the Docker container named 'hoohacks2021-first-container'.
    docker rm hoohacks2021-first-container
    ```
- Create a Docker image:
  * ```
    # Moves into our presentationFiles directory and builds a Docker image using the create-react-app template.
    cd presentationFiles && docker build --tag hoohacks2021-app:0.0.1 .
    docker images
    ```
- Start a Docker image using a created image:
  * ```
    # Start a detached container running our image; sending incoming port 80 traffic to container's port 3000.
    docker run --detach --publish=80:3000 hoohacks2021-app:0.0.1
    ```