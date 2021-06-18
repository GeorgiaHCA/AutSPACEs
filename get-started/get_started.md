# What can all be found in this repo?

Please follow the below mind map to understand the impotant topics to concentrate on the repository

![alt text](https://github.com/alan-turing-institute/AutSPACEs/blob/lotty-repo-refresh/get-started/github_mindmap.png)


# Steps to start the website

## Setup:

Before starting, please check that the following minimum requirements have been completed.

1. Install [Docker](https://www.docker.com/products/docker-desktop). (Latest stable release, version 20.10.5 or greater)
2. Install [Docker Compose](https://docs.docker.com/compose/install/). (Latest stable release, version 1.28.5 or greater)
3. Create an [Open Humans](https://www.openhumans.org/) account.
4. Some version of Python 3.x.x.

### Some prerequisites and know-hows for installing Docker:

### Windows 10:

- Download Docker from the official Website named as "Docker Desktop for Windows"
- Make sure to Download and install the [Linux kernel update package](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi).
- When Docker is downloaded completely, go to the location where the application downloaded and double click on the Docker Desktop Installer.exe to run the installer.
- When prompted  **Install required Windows components for WSL 2** option is selected on the Configuration page.
- Follow the instructions on the installation wizard to authorize the installer and proceed with the install.
- When the installation is successful, click **Close** to complete the installation process.
- Open the Docker for Desktop, try the tutorial to understand to create and build a docker image. In order to share the image, create an account from the Docker hub.
- In this Docker is successfully and running!

# How to start website

If you're interested in building and running the AutSPACE platform, read on!

## Setup

Before starting, please check that the following minimum requirements have been completed.

1. Install [Docker](https://www.docker.com/products/docker-desktop). (Latest stable release, version 20.10.5 or greater)
2. Install [Docker Compose](https://docs.docker.com/compose/install/). (Latest stable release, version 1.28.5 or greater)
3. Create an [Open Humans](https://www.openhumans.org/) account.
4. Some version of Python 3.x.x.

## Installation

Project installation can be tricky, but like all things, progress is made one step at a time.

1. [Clone](notion://www.notion.so/Steps-to-start-the-website-e23d106a13464002aae37d6ad34c5d4b#cloning-the-repository) the repository at [AutSPACEs](https://github.com/GeorgiaHCA/AutSPACEs)
2. Within the `config` directory, copy `.env.template` to `.env`.
Note: ***DO NOT UPLOAD THESE .ENV FILES ONTO GITHUB*** It's the equivalent of posting your passport ID on Twitter. Don't do it.

### Open Humans Project Creation

This step is a little tricky, but you're almost there.

1. Login to [OpenHumans](notion://www.notion.so/openhumans.org).
2. Navigate to [Manage Project](https://www.openhumans.org/direct-sharing/projects/manage/).
3. Create a new Oauth2 Data Request Project on Open Humans.
4. Populate the required fields as directed.
5. In the `Redirect URL` field, enter `http://localhost:8000/openhumans/complete`.
6. Click `Create Project`.

You'll need to obtain the Client ID and Client Secret for the OAuth project you've created.

1. Navigate to [Manage Project](https://www.openhumans.org/direct-sharing/projects/manage/).
2. Click the newly created project.
3. Copy and paste somewhere safe the `Client ID` and `Client Secret` under `OAuth2 Credentials`.

### Project Configuration

Within `.env` there are four different fields that must be populated for the project to build.

### Django Secret Key Generation

1. Open `.env` in your favorite editor, and using `python3`, follow the instructions under the `django` header to copy/paste the generated secret key to `DJANGO_SECRET_KEY`

The following...
`DJANGO_SECRET_KEY=__CHANGEME__`

should look something like this, where XXXXXXXXXXXXXXXXXXXXXX is the generated key.
`DJANGO_SECRET_KEY=XXXXXXXXXXXXXXXXXXXXXX`

### Configuring OpenHumans

Further down the `.env` file, you should see three texts: `OPENHUMANS_CLIENT_ID`, `OPENHUMANS_CLIENT_SECRET`, and `OPENHUMANS_APP_BASE_URL`.

1. Copy the `Client ID` and `Client Secret` that you've copied previously into `OPENHUMANS_CLIENT_ID` and `OPENHUMANS_CLIENT_SECRET`, respectively.
It should look something like this, where XXXXXXXXXXXXXXXXXXXXXX are the inputted information.

```
OPENHUMANS_CLIENT_ID=XXXXXXXXXXXXXXXXXXXXXX
OPENHUMANS_CLIENT_SECRET=XXXXXXXXXXXXXXXXXXXXXX

```

1. Type the following url into `OPENHUMANS_APP_BASE_URL`.
It should look like this!

```
OPENHUMANS_APP_BASE_URL="<http://localhost:8000>"

```

2. You're done!

## Running the Project

The project builds and runs in a self-contained environment called Docker. This means developer environments are preserved, and you don't need to mess with any dependency management or installation.

1. Open up Terminal or Command Line in the root level of the repository and execute the following command: `./docker-run.sh`
2. Open your browser to `http://localhost:8000`

*This will display the AutSPACEs website.* Yay!

Note: Please note that certain aspects of the website may not be fully functional. ;)

## Glossary

- Clone: make a copy of all the files and folder in the repository on your computer
- Docker: a tool which creates an individual place (called a 'container') for a software project which is set up for that project to run.
- Fork: your fork is your own personal copy of the repository, where you can make changes without affecting the main repository until you make a pull request.
- Git: is a free, open source tool that is useful for version control (keeping a record of and managing changes to software code)
- GitHub: GitHub is an online tool which makes it easier for people to work collaboratively using Git.
- Repository: this is a place which holds all the files and folders specific to one project. On GitHub, this is where people can work on a project together.
- Root level: this is the level of the project which contains all the others as files and subfolders
- Terminal: this is an application on your computer which allows you to use code to modify your computer's software and files.

## How-Tos

### Cloning the Repository

1. **Fork** the repository by clicking on the Fork icon at the top right hand corner of the page.
2. Above the list of files, click the green **Code** button.
3. Clone the repository into your local directory.
4. Open terminal to the project directory.
5. Type 'git clone', and then paste the URL you copied earlier. It will look like this, with your GitHub username instead of YOUR-USERNAME:

> $ git clone https://github.com/YOUR-USERNAME/AutSPACEs

1. Press enter. Your local clone will be created.

### Extra Tips

*If you aren't sure how to get to the root repository, you can find it more easily by following these steps:*

1. Type `git config --global alias.root 'rev-parse --show-toplevel` into your terminal. This will create a simpler command to take you to the root repository.
2. Type `cd $(git root)` into your terminal. This will take you to the root of the repository you are in.

### Docker overview

You might find the chapter on [reproducible computational environments](https://the-turing-way.netlify.app/reproducible-research/renv.html) and spectifically the section on [containers](https://the-turing-way.netlify.app/reproducible-research/renv/renv-containers.html) in *The Turing Way* useful!

# Code
* The main code is found in the folder called [server](https://github.com/alan-turing-institute/AutSPACEs/tree/main/server)
* This code can be modfied accordingly. 

