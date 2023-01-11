# **Docker Installation Script for Ubuntu**

This script automates the installation and configuration of Docker on Ubuntu systems. The script will install the latest version of Docker, remove any old versions, and configure it to start on boot with systemd.

## **How to Use**

1. Save the script to your Ubuntu system, and give it execution permissions:

```
Copy code
wget wget https://raw.githubusercontent.com/Monzim/script/main/docker/docker-install.sh
chmod +x docker-install.sh

```

1. Run the script as a superuser:

```
Copy code
sudo ./docker-install.sh

```

1. Follow the prompts to configure your installation. The script will ask if you want to manage Docker as a non-root user and if you want to configure Docker to start on boot with systemd.
2. Verify that Docker is working by running the hello-world image:

```
Copy code
docker run hello-world

```

## **What's Going On**

- The script will first remove any old versions of Docker that are currently installed on the system.
- Then it sets up the official Docker repository, adds the GPG key, and installs the latest version of Docker.
- Next, it will verify that the installation was successful by running the hello-world image.
- Then it will give an option to manage Docker as a non-root user, if you select yes it will create a UNIX group called docker and add your user to it.
- Lastly, it gives the option to configure Docker to start on boot with systemd.
- At the end, it will notify the user that Docker is now installed successfully.

## **Note**

- When you run this script you will prompt with multiple options and answers need to be given in 'y' or 'n' format only
- Also, note that this script will download and install the latest version of Docker.
- If you are behind a proxy, you may need to configure it for the script to download and install the necessary packages.
- The script is verified on Ubuntu 20.04 LTS and should also work on other versions.
- It is assumed that you have all the necessary permissions to run this script.
- Also, user need to log out and log in after the script execution if they have selected the option to manage Docker as a non-root user

This script helps you to easily and quickly set up Docker on your Ubuntu system. Let me know if you have any issues or questions.