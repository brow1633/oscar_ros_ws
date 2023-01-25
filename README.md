# Steps to begin #

## Windows ##
- Install VS Code (https://code.visualstudio.com/Download)
- Open a windows command prompt and type ```wsl --install -d Ubuntu```
- Reboot your computer, and let Ubuntu fully install upon startup and set your username and password.
- Install Docker Desktop (https://docs.docker.com/desktop/install/windows-install/), after installation you'll be asked to re-login.
- Open an Ubuntu shell by hitting the start button and typing "ubuntu"
- Create an SSH key and add it to your Github account (ref: https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

  - Run ```ssh-keygen -t ed25519 -C "your_email@example.com"```, with your email address, and hit enter 3 times
  - Open your .bash_profile in VS Code ```code ~/.bashrc```
  - Add the following to the bottom:
  
    ```
    if [ -z "$SSH_AUTH_SOCK" ]; then
        # Check for a currently running instance of the agent
        RUNNING_AGENT="`ps -ax | grep 'ssh-agent -s' | grep -v grep | wc -l | tr -d '[:space:]'`"
        if [ "$RUNNING_AGENT" = "0" ]; then
          # Launch a new instance of the agent
          ssh-agent -s &> $HOME/.ssh/ssh-agent
        fi
        eval `cat $HOME/.ssh/ssh-agent`
        ssh-add ~/.ssh/id_ed25519
    fi
    ```
  - Copy your public key by running ```cat ~/.ssh/id_ed25519.pub```, and add it to your github account (https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account#adding-a-new-ssh-key-to-your-account)
- Clone this repository into your home directory, and navigate into it ```git clone https://github.com/brow1633/oscar_ros_ws.git --recurse-submodules && cd oscar_ros_ws```
- Open VS Code within the WSL shell ```code .```  You may get a warning about unsafe repositories, you can ignore this.
- Install the dev-containers VS Code extension (https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
- In the left-hand corner, click the green dev-containers icon and select "Reopen in Container" and let it fully install
- Once the container has finished building, you're all setup!  You won't have language server processing until you build the project for the first time, so go ahead and open a new VS Code Bash terminal (an sh terminal opens by default, yuck) and type ```colcon build```
  - *Note:* ```colcon build``` has had an alias attached which automatically runs ```--symlink-install``` and generates files required for language processing in VS Code

## Linux ##
1. Install VS Code
2. Install Docker ```sudo apt-get install docker```
3. Use the steps from Windows
