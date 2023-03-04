# Python DevContainer Setup

This is a template for setting up a Python development environment in a Docker container. It uses the [VSCode Remote - Containers](https://code.visualstudio.com/docs/remote/containers) extension to create a containerized development environment. To use this template, you will need to have Docker installed on your machine. You can find installation instructions [here](https://docs.docker.com/get-docker/).

## Getting Started

1. Clone this repository to your local machine.
2. Open the repository in VSCode.
3. Wait for VSCode to recognize the `.devcontainer` folder and click on "Reopen in Container" or click the green button in the lower left corner of the window that says "Reopen in Container".
4. Wait for the container to build and start. This may take a few minutes. It will install the Python version specified in the `devcontainer.json` file and install the dependencies specified in the `pyproject.toml` file. You can change the Python version by changing the `pythonVersion` property in the `devcontainer.json` file.
5. In this setup, `Poetry` is used to manage dependencies. You can install dependencies by running `poetry add <package-name>` in the terminal. You can also install dependencies by editing the `pyproject.toml` file and running `poetry install` in the terminal.
6. The `post-install.sh` script will run after the container is built. You can use this to run any commands you want to run after the container is built. For example, you can use this to run a script that sets up a database or runs migrations. Just add your commands to the `post-install.sh` file and they will run after the container is built.

## Using Poetry

To use `Poetry` check the official [docs](https://python-poetry.org/docs/). Here are some useful commands:

### Poetry Commands

```bash
# Install dependencies
poetry install

# Add a dependency
poetry add <package-name>

# Remove a dependency
poetry remove <package-name>

# Update a dependency
poetry update <package-name>

# Run a script
poetry run <script-name>

```
To run your code make sure to enter the virtual environment by running `poetry shell` and then run your code. To exit your virtual environment run `exit` in your terminal. To test this setup try to run the code inside of the `Jupyter Notebook` file in the `src` folder. You might have to choose the right kernel. Chose the `Python` kernel that is inside of the `Poetry` virtual environment. The `Poetry` virtual environment should be listed as the first option and be named something similar to ".venv (Poetry 3.11.2)".

If you feel like poetry is slow you can try clearing the cache by running the following command:

```bash
poetry cache clear --all pypi
```
This should resolve any issues with poetry being slow.

