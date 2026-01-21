I set up a VPC with 2 public and 2 private subnets:
<img width="975" height="238" alt="image" src="https://github.com/user-attachments/assets/8183670e-ea06-4c79-abd0-0b89be9903ab" />
Attached Internet Gateway to one public subnet:
<img width="936" height="164" alt="image" src="https://github.com/user-attachments/assets/490739c2-5895-4e35-92f7-8da6271b5f35" />
I borrowed an EIP to use it for the NAT gateway:
<img width="978" height="150" alt="image" src="https://github.com/user-attachments/assets/b757fd6e-dedb-49d7-ab2d-1fc53c9b9cb7" />
I routed the the public and private subnets to the IGW and NATGW respectively:
<img width="947" height="68" alt="image" src="https://github.com/user-attachments/assets/7e2bbaed-30cb-41c9-b292-168c2ad77ac3" />
<img width="948" height="281" alt="image" src="https://github.com/user-attachments/assets/03545148-2728-4d63-9b4f-58b01c74e6ad" />
I loaded up two EC2 instances with the following properties:
Public EC2 SG - allow SSH/HTTP only from your IP, linked with the public subnet
Private EC2 SG - allow only internal access (e.g. from public EC2 or Bastion host), linked with private subnet
<img width="948" height="132" alt="image" src="https://github.com/user-attachments/assets/57ff3bd3-4dd2-4889-bda0-d46cceae7a0f" />

