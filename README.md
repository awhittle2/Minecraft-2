# Minecraft-2.0 - [Video Link](https://clipchamp.com/watch/CCHYsbnp36w)
## Background

### What Will We Do?

Make a Minecraft server using an AWS account that is able to auto reboot and shutdown with systemd services

### How Will We Do it?

Using Git/GitHub, Terraform, AWS and the AWS command line interface, and Docker!

## Requirements

- Personal computer/laptop with WiFi or Ethernet access
- An AWS account
     - Note: This tutorial is made using the AWS Academy, so results may vary if you're using a regular AWS account
- Git installed
    - Linux: `sudo apt install git-all` or `sudo dnf install git-all`
    - MacOS: `git --version`
    - Windows: [Installation Link](https://git-scm.com/download/win)
    - [Help](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
 - Terraform installed
     - Linux - Debian-based: [Script](https://github.com/awhittle2/Minecraft-2.0/blob/scripts/linux-terraform-install.sh)
     - Linux - RHEL-based: [Script](https://github.com/awhittle2/Minecraft-2.0/blob/scripts/linux-terraform-install2.sh)
     - MacOS: [Script](https://github.com/awhittle2/Minecraft-2.0/blob/scripts/mac-terraform-install.sh)
     - Windows - Chocolatey: `choco install terraform`
     - [Help](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)
 - AWC CLI installed
     - Linux: `curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
               unzip awscliv2.zip
               sudo ./aws/install`
     - MacOS: `curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
               sudo installer -pkg AWSCLIV2.pkg -target /`
     - Windows: `msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi`
     - [Help](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
 - A Minecraft Client
     - Note: This will still work without one, however, you wouldn't be able to play minecraft without it!

## Diagram of My Steps

![image of my steps](./images/my-diagram.png)

## Diagram of Your Steps

![image of your steps](./images/your-diagram.png)

## Explanation of Terraform Script

## List of Commands to Run

```bash
# Clone the repository
git clone https://github.com/awhittle2/Minecraft-2.0.git
cd Minecraft-2.0/

# Enter your AWS account details
```
What you'll need:
- Your AWS Access Key ID
- Your AWS Secret Access Key
- Your AWS Session Token

Where to go to find it:
1. Start your Learner Lab
2. Click `AWS Details`
3. Click `AWS CLI: Show`

![where to find aws creds](./images/aws.png)

```bash
# Replace the underscores with your AWS credentials
export AWS_ACCESS_KEY_ID=___
export AWS_SECRET_ACCESS_KEY=___
export AWS_SESSION_TOKEN=___

# Make sure that main.tf is there
ls

# Initialize the terraform prjoect
terraform init

# Apply the changes
terraform apply

# Wait about 5 minutes for it to create the instance and run the set-up script
```

## How to connect to the Minecraft server once it's running?

1. Load up your Minecraft client
3. Click on `Multiplayer`
   ![load minecraft](./images/minecraft-multiplayer.png)
5. Select `Add Server`
   ![server page](./images/minecraft-add-server.png)
7. Under `Server Address` enter in the ip address that the terraform script outputted with `:25565` afterwards
   ![add server page](./images/minecraft-server-address.png)
9. Click `Done`
10. Wait until Minecraft is able to connect
    ![minecraft connection](./images/minecraft-connection.png)
12. Click `Join Server`
    ![join server](./images/minecraft-join.png)
14. Have fun!
