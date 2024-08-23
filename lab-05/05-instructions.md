# Lab 05 - AWS Config with SSH and Outputs

Here you will build on Lab 04 by adding proper SSH support. You'll also learn how to use outputs to have Terraform tell you information you need to know, such as the IP address and name of an instance.
Finally, we'll use cloud-init to provide additional configuration details to our build.

> Note: This lab is a bit more in-depth, so go slow, and take it step-by-step. This time we'll be using a current Ubuntu image. If you get stuck, view the solution in the /solution directory.

> **IMPORTANT!** You will need the appropriate networking infrastructure on AWS for this lab to work. A typical AWS account will already be setup for proper access. However, if you have made changes to your AWS networking, then you may encounter issues. From a high-level, you will need the following: a properly setup VPC and subnet; a properly configured route table; and an Internet gateway attached to the VPC and route table. If you have questions, feel free to contact me!

## Create a directory structure

Create two new directories: instances and keys.
For example: `mkdir {instances,keys}`

- Your main.tf file will go into the instances directory. This is the directory where you will run your Terraform commands.
- Your SSH keys will be placed in the keys directory.

## Create an SSH key pair

You will need openssh or another SSH tool installed.

- Run the command `ssh-keygen` to create an SSH key pair.

- Name the key "aws_key" and save the key to the "keys" directory. (You can also specify the path and key name with the `-f` option of the ssh-keygen command.)

> NOTE: The solution does not have a key pair, you will have to take care of that part!

## Build your Terraform files

- Make the following files within the instances directory:

  - version.tf
  - provider.tf
  - main.tf
  - outputs.tf

- In version.tf, use the standard terraform block code that you have used in Lab 04.
- In provider.tf, use the standard provider block code that you have used previously. Change the region to meet your geographical requirements.
- Copy the code from code-main.txt to your main.tf file.
  - Analyze the main.tf file. 
  - Find the block named <resource "aws_key_pair"> and add your SSH public key where it says <public_key>
- Copy the code from code-outputs.txt to your outputs.tf file. 
  - Analyze the outputs.tf file. 
  - What information will Terraform supply you with when the terraform apply is complete?

> IMPORTANT!! WATCH FOR ERRORS!!

## Initialize, validate, and apply your Terraform configuration

- Your working Terraform directory is /instances.
- Use the commands you have learned to initialize, format, validate, plan, and finally, apply your configuration.
- What information was outputted to you in the terminal?

> NOTE: If you lose the outputted information just type `terraform output` to see it again!

- Once the infrastructure has been built, view it within your AWS console.

> NOTE: You might need to wait a minute or two for the virtual machine to initialize.

## SSH into your new virtual machine

Using the information that was outputted, SSH into your instance.

For example, you might do something similar to this:

`ssh -i "../keys/aws_key" ubuntu@<ip_address>`

> NOTE: If you were to look at the AWS console and view the SSH option, it would show "aws_key.pem" but the .pem extension will not work because we created a standard openssh key pair, not an AWS key pair.

Make sure that you can access the system. Run commands on the remote system such as:

`cat /etc/os-release`

and

`ping example.com`

and

`top`

When done, exit out of the SSH session.

## Destroy the infrastructure

Destroy the infrastructure with the command:

`terraform destroy`

---

### ❣️ That's it. You completed the final lab!

### GREAT WORK! 👍

Remember, if you are interested in learning more about Terraform and possibly obtaining the Terraform Certification, see the following links:

- On [O'Reilly](https://learning.oreilly.com/course/hashicorp-certified-terraform/9780138195366/)
- On [InformIT](https://click.linksynergy.com/link?id=g%2f%2f2PZbywdw&offerid=145238.248089780138195397&bids=145238.248089780138195397&bids=145238.248089780138195397&type=2&murl=https%3a%2f%2fwww.pearsonitcertification.com%2ftitle%2f9780138195397&)

---
