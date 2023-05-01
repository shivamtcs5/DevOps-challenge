Using Terraform code to deploy three-tier architecture on azure:

3-tier architecture consists of following components:
Web Tier: This tier is responsible for user interaction and provides the interface for users to interact with the application. The web tier typically consists of a web application that is hosted on a web server. In Azure, you can use Azure App Service or Azure Functions to host your web application.

Application Tier: This tier is responsible for the business logic of the application. It performs processing, data validation, and communication with other components of the application. In Azure, you can use Azure Functions or Azure Kubernetes Service (AKS) to host your application tier.

Data Tier: This tier is responsible for storing and retrieving data used by the application. In Azure, you can use Azure SQL Database or Azure Cosmos DB to host your data tier.

Solution:
One virtual network tied in three subnets. Each subnet will have one virtual machine. First virtual machine -> allow inbound traffic from internet only. Second virtual machine -> entertain traffic from first virtual machine only and can reply the same virtual machine again. App can connect to database and database can connect to app but database cannot connect to web.

For the solution, we have created below mentioned modules:
resourcegroup - creating resourcegroup networking - creating azure virtual network and required subnets securitygroup - creating network security group, setting desired security rules and associating them to subnets compute - creating availability sets, network interfaces and virtual machines database - creating database server and database All the stacks are placed in the modules folder and the variable are stored under terraform.tfvars

To run the code you need to append the variables in the terraform.tfvars

Each module consists minimum two files: main.tf, vars.tf

resourcegroup and networking modules consists of one extra file named output.tf
