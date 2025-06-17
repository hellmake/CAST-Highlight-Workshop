---
title: "Installing the Code Reader"
chapter: true
weight: 4
---

# Installing the Code Reader

As a ***SaaS*** product, **CAST Highlight** doesn't require any web server to run on your environment to display your portfolio results. However, its goals are also to be ***non-intrusive*** and to ensure that your confidential information never leaves your company's premises.

To that end, we will be performing the actual analysis of the applications' source code locally and we'll upload the results of the scan to the SaaS portal, which only contains meta-data.

## Requirements
This step requires access to a computer with a 64bit Windows, Linux (Debian or Fedora recommended), or MacOS.

If you'd rather use a cloud-based instance, we can quickly spin one up on EC2. A complete tutorial on how to do this is available [here](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/EC2_GetStarted.html). It basically boils down to: 
- Launching a fresh instance (we recommend using the *Microsoft Windows Server 2019 Base* AMI of type *t3.large*)
- Creating a private key (.pem) file
- Decrypting the administrator password
- RDPing to the machine and installing your favourite browser.

Then you should copy the applications to scan onto the EC2 instance, and from there log in to your freshly minted account at https://demo.casthighlight.com where you'll proceed to the next step.
![Highlight Portal in an EC2 Instance](/images/Install-3.png)

## Downloading the Code Reader

From the ***Application Scans*** page you can simply click on the **Download Code Reader** button and it will take you to the [Download Page](https://doc.casthighlight.com/codereader/) where you can grab the installer that fits your OS.
![Download Code Reader](/images/Install-1.png)

## Installation process
For a Windows/EC2 machine, the file *CAST.Highlight.Code.Reader_1.a.bb_x64-setup* can be executed and will enable you to choose a Language (we'll go with English here) for the setup wizard. You can
- Click on ***Next***
- Read the agreement and select the *"I Agree"* option
- Select an installation folder (as you can see, the Code Reader doesn't take much space)
- Select a *Start Menu* folder
- And finally monitor the installation's progress (it shouldn't take more than a couple minutes)
... and you're set.
![Installation complete](/images/Install-2.png)

### Onto the actual scanning of code
Leave the *"Run CAST Highlight Code Reader"* option checked and click on ***Finish***...