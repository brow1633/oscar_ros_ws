# Steps to begin #

## Windows ##
1. Install VS Code (https://code.visualstudio.com/Download)
2. Open a windows command prompt and type ```wsl --install -d Ubuntu```
3. Reboot your computer, and let Ubuntu fully install upon startup and set your username and password.
4. Install Docker Desktop (https://docs.docker.com/desktop/install/windows-install/)
5. Install the dev-containers VS Code extension (https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## Linux ##
1. Install VS Code
2. Install Docker ```sudo apt-get install docker```
3. Install the dev-containers VS Code extension (https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
4. Clone this repository
5. Open the repository in VS Code
6. Click the green icon in the bottom left-hand corner and select "Open Folder in Container"
7. (Optional) To allow Git SSH key forwarding, follow https://code.visualstudio.com/remote/advancedcontainers/sharing-git-credentials
8. (Optional) To enable GUI elements from the docker container (Gazebo, Rviz, etc), run xhost + on the host.  *This is potentially dangerous*
