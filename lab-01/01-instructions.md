# Lab 01 - Install Terraform

Welcome to the first lab! 
In this lab you will install the Terraform CLI on to your system. 
Remember, in this course, I am demonstrating on a Debian Linux virtual machine. Let's go!

## Install Terraform from Hashicorp:

**Option #1** - Install using your package manager.
https://developer.hashicorp.com/terraform/install

Locate your operating system and install Terraform following the directions.

> Note: For macOS, I recommend the [HomeBrew](https://formulae.brew.sh/formula/terraform) install. For Windows, I recommend using a WSL2 Ubuntu VM (and installing with the Linux method) or the [Chocolatey](https://community.chocolatey.org/packages/terraform) install.

**Option #2** - Install the binary.
https://releases.hashicorp.com/terraform 

Locate the latest version for your platform, download it, verify the checksum, unzip it, and copy it to your binaries directory (for example, /usr/bin or /usr/local/bin).

> Note: See the end of this lab document for more details on the binary installation. Remember that unlike the package manager installation, this option will not allow for auto-updating of the Terraform binary.

If you have any issues, ASK QUESTIONS!

> Note: Additional Terraform installation walk-throughs can be found [here](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli).

## Verify that Terraform is installed and view the version.
`terraform version` 

or

`terraform -v`

---
## Binary install (Linux)

- Access https://releases.hashicorp.com/terraform  

- go to the current version > then platform

- Copy the binary with either: 
  - `curl -Lo ./terraform.zip  <HTTP_URL>`
  - or  
  - `wget <HTTP_URL>` 

- Check with sha256sum
  - Download the checksums file.
  - Run the command `sha256sum <filename.zip>`
  - `cat` the checksum file
  - Compare the two checksums and make sure they match

- Rename to terraform.zip if you used `wget`.
- Unzip: `unzip terraform.zip`
- Move it to part of your executable path. For example:
  - `mv terraform /usr/bin`
- Check that you can run it from anywhere:
  - `terraform version`

Now you should be able to run the program from any directory.

> Note: Other binary installs for Windows, macOS, etc, will vary.