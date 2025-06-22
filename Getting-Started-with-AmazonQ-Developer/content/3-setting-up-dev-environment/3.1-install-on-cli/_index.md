---
title: "Installing Amazon Q Developer on CLI"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

#### Installing Amazon Q Developer on CLI

Amazon Q Developer CLI supports macOS and Linux (including Ubuntu). Below are concise installation steps based on the official AWS documentation.[[1]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html)

#### 1. Install on macOS

- Download the Amazon Q CLI `.dmg` installer from the official AWS page.  
- Open the `.dmg` file and drag the app into the Applications folder.  
- Launch the Amazon Q app and follow the instructions to activate shell integrations so you can use the `q` command in the terminal.  
- Log in with AWS Builder ID or IAM Identity Center.

Or you can quickly install via Homebrew:

```bash
brew install amazon-q
```

![alt text](/images/3-setting-up-dev-environment/3.1-install-on-cli/image.png?width=90pc)

*Figure 1: Installing Amazon Q CLI on MacOS*


#### 2. Install on Linux (Ubuntu)

- Download the official `.deb` package:

```bash
wget https://desktop-release.q.us-east-1.amazonaws.com/latest/amazon-q.deb
```

- Install the package:

```bash
sudo apt-get install -f
sudo dpkg -i amazon-q.deb
```

- Launch Amazon Q CLI:

```bash
q
```

- Log in with AWS Builder ID or IAM Identity Center.

> Note: This method requires a GUI environment to run the desktop app.

Alternatively, you can install using AppImage (also requires GUI):

```bash
chmod +x amazon-q.appimage
./amazon-q.appimage
```

#### 3. Using on Windows

Amazon Q Developer CLI does not have a native Windows installer. To use it on Windows, you need to install **Windows Subsystem for Linux (WSL)** and run Amazon Q CLI in this virtual Linux environment.

- Microsoft WSL installation guide:  
  https://learn.microsoft.com/windows/wsl/install

- After installing WSL and Ubuntu, follow the Linux installation instructions above in the WSL terminal.


#### 4. Checking and Troubleshooting

- Use the following command to check installation status:

```bash
q doctor
```

- If you encounter login errors, rerun:

```bash
q login
```

- To report bugs or issues, use:

```bash
q issue
```

![alt text](/images/3-setting-up-dev-environment/3.1-install-on-cli/image-3.png?width=60pc)

*Figure 2: Checking and troubleshooting*
