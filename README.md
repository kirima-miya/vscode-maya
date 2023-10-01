# MayaCode for Dev Container Support

This project is a fork of [artbycrunk/vscode-maya](https://github.com/artbycrunk/vscode-maya)

It has been updated to support execution from [Dev Container](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

# Developer Notes

## Getting Started

After cloning the repo, run `npm install` to install the dependencies.

## Compiling the extension

Run `npm run package` to create a .vsix file.

## Installing the extension

1. Move the .vsix file to your project folder.

2. Add the `remoteEnv` and `customizations` property to the `devcontainer.json` file in your project.

    ```json
    {
        // https://code.visualstudio.com/remote/advancedcontainers/environment-variables
        // https://containers.dev/implementors/json_reference/#variables-in-devcontainerjson
        "remoteEnv": {
            "LOCAL_WORKSPACE_FOLDER": "${localWorkspaceFolder}",
            "CONTAINER_WORKSPACE_FOLDER": "${containerWorkspaceFolder}"
        },
        "customizations": {
            "vscode": {
                "settings": {
                    "mayacode.hostname": "host.docker.internal"
                },
                "extensions": [
                    "${containerWorkspaceFolder}/.mayacode/mayacode-devcontainer-1.0.0.vsix"
                ]
            }
        }
    }
    ```
