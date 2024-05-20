# Bend Language Devcontainer

## Overview

This project uses a devcontainer to provide a consistent development environment with Rust and GPU support for the new [Bend] (https://github.com/HigherOrderCO/Bend) language. The devcontainer is based on an NVIDIA CUDA image and includes the Rust programming language along with the `hvm` and `bend-lang` tools.

## Prerequisites

Before you can use the devcontainer, ensure you have the following installed on your local machine:

1. **Docker**: You can download and install Docker from [here](https://www.docker.com/products/docker-desktop).
2. **Visual Studio Code**: Download and install Visual Studio Code from [here](https://code.visualstudio.com/).
3. **DevContainers Extension for VS Code**: Install the DevContainers extension in VS Code. You can find it in the Extensions Marketplace or install it directly from [here](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers).

## Using the DevContainer

Follow these steps to use the devcontainer:

1. **Clone the Repository**:
    ```sh
    git clone https://github.com/ap0phasi/bend-lang-devcontainer.git
    cd your-repo
    ```

2. **Open the Repository in VS Code**:
    - Open Visual Studio Code.
    - Go to `File` > `Open Folder...` and select the cloned repository folder.

3. **Reopen in DevContainer**:
    - Once the folder is open in VS Code, press `F1` to open the Command Palette.
    - Type `Dev Containers: Reopen in Container` and select it.

VS Code will now build the Docker image specified in the `devcontainer.json` file and open the project in the devcontainer. This process may take some time, especially the first time, as it needs to download the Docker image and set up the environment.

## Running Bend

Once inside the container, you can create .hvm files, and populate with examples from HigherOrderCO: https://github.com/HigherOrderCO/Bend/tree/main/examples. 

You should be able to run with either:

```
bend run yourfile.bend
```

or

```
bend run-cu yourfile.bend
```

## Additional Information

- The Dockerfile used for the devcontainer is located at `.devcontainer/Dockerfile`.
- Configuration for the devcontainer is specified in the `.devcontainer/devcontainer.json` file.
- The devcontainer includes:
  - Rust (with nightly toolchain)
  - CUDA toolkit (NVCC is required for bend run-cu)
  - `hvm` and `bend-lang` tools

## Troubleshooting

- If you encounter any issues with the devcontainer setup, ensure that Docker is running on your local machine.
- Make sure you have the latest versions of Docker and VS Code installed.
- If the build process fails, check the output in the `Terminal` and `Problems` panels in VS Code for more details.

## Contributing

Feel free to open issues or submit pull requests if you have suggestions or improvements.

I don't know anything about Bend or Rust really, I made this so I could experiment and learn, so hopefully it is some help. 

## License

This project is licensed under the MIT License.

