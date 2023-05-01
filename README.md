# DevOps-challenge

Using Terraform code to deploy three-tier architecture on azure

For the solution, we have created and used five modules:

resourcegroup - creating resourcegroup
networking - creating azure virtual network and required subnets
securitygroup - creating network security group, setting desired security rules and associating them to subnets
compute - creating availability sets, network interfaces and virtual machines
database - creating database server and database
All the stacks are placed in the modules folder and the variable are stored under terraform.tfvars

To run the code you need to append the variables in the terraform.tfvars

Each module consists minimum two files: main.tf, vars.tf

resourcegroup and networking modules consists of one extra file named output.tf
