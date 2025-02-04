# 4640_lab4_Kasim
## General Set-Up
1. create a terraform file and a cloud init config file
2. in the cloud init config file, specify the user you want to connect as, add the public key you will use, and include the packages you want to use.
3. in the terraform file, set the provider in a terraform block as well as the aws provider.
4. specify the aws ami you want to use in a data block
5. create a VPC, subnet, IGW and route table using their respective blocks. make sure to reference the necessary ID's for each block
6. make route and route table association resources. in route make sure you give it a destination and add your route table ID. in the association add the route table id and subnet id.
7. create your security group and give it a name and reference the vpc id.
8. then create your rules with the ingress and egress rule resource blocks. make sure to specify the protocol and the ports
9. finally create your instance with the aws_instance resource block. reference the ami and security group you made before and give the instance a type like "t2.micro". Additionally, use user_data to put the cloud-config file into the instance. you can use it like this: `user_data = file(file-path)`
10. once your done configuring all your files you can use `terraform init` to initialize the folder with your config files
11. use `terraform fmt` to format your .tf file
12. then you can validate your configuration file with `terraform validate`
13. after you can create an plan that lets you view your changes with `terraform plan -out plan-name`
14. finally use `terraform apply` to create your infrastructure
15. you can also destroy it when not need with `terraform destroy`
## new SSH key pair command
`ssh-keygen -t ed25519 -f ~/.ssh/key-name -C "lab4 key"`
## Terraform command
- terraform init: initializes current folder to use terraform in
- terraform fmt: formats the .tf file
- terraform validate: verifies the terraform configuration file
- terraform plan -out plan-name: makes a plan that lets you see your changes
- terraform apply: executes the .tf and provisions your infrastrucure
- terraform destroy: deletes your running infrastructure
