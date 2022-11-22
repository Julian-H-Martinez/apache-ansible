## Name
Ansible Container Build

## Description
This project allows the user to build an image and run a container that will allow the user to run an ansible-playbook
The playbook will be created with multiple roles that should run an apache server and establish connection through your localhost

## Installation
You can build and run container from CLI or IDE
Below lays out instructions on how to build/run from both

## From CLI
The only time your working folder should be considered is when building your image
Since dockerfile sits inside of a .devcontainer please be sure to change directory into .devcontainer
The commands assume that you are in .devcontainer of the NGINX-ANSIBLE project
Please note that the term 'the user' is referencing you as the developer running the commands

# Building the Image
docker build -t <imageTagName> -f ansible . 
    NOTE: <imageTagName> is arbitrary but best practice is to follow semantic versioning format: imageName:0.0.1

# Running the Container
docker run -dit --name <containerName> <imageTagName>
    NOTE: <containerName> is arbitrary; it is to better help the user remember the container name which will be needed later
    NOTE: <imageTagName> is the tag name the user assigned the image in the Build stage

# Execute into container cli
docker exec -it <containerName> ash
    NOTE: <containerName> is name the user assigned in running the container

## Project status
- Project is a work in progress and currently can build an image and run the container
- Ansible is being installed with the image and should be able to run playbook
    - currently playbook is setup with 2 shell roles
    - currently working on getting apache server role configured and tasks setup

## From IDE
The project was built using VS Code IDE and the following instructions are based on VS Code IDE
Please feel free to add other IDE as needed otherwise engineer will update IDE instructions periodically
Please note that the term 'the user' is referencing you as the developer running the commands

# VS Code
Open Command Palette
    - Toolbar: View -> Command Palette
    - Shortcut: ctrl+shift+p
Search:
    - Dev Containers: Open Folder in Container...

This should reopen VS Code from container view, meaning you won't have to you the docker exec command from earlier.
Simply open a new terminal to be able to run commands from inside your container (similarly to being in a virtual machine)
Open New Terminal
    - Toolbar: Terminal -> New Terminal
    - Shortcut: ctrl+shift+` (backtick '`' is located next to number 1 key on keyboard)

# Editing this README
When you're ready to make this README your own, just edit this file and use the handy template below (or feel free to structure it however you want - this is just a starting point!). Thank you to [makeareadme.com](https://www.makeareadme.com/) for this template.

## Suggestions for a good README
Every project is different, so consider which of these sections apply to yours. The sections used in the template are suggestions for most open source projects. Also keep in mind that while a README can be too long and detailed, too long is better than too short. If you think your README is too long, consider utilizing another form of documentation rather than cutting out information.
