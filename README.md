# Security-and-NACL


## 2. Project Steps and Commands

### 2.1. Go to Subnet page
![Create subnet](https://github.com/user-attachments/assets/c72dc682-7dea-4940-9042-758f9c2eca96)

![Enter the infos](https://github.com/user-attachments/assets/9590de1d-f4aa-495b-a01f-72a72329f5d9)

![Set your inbound rules](https://github.com/user-attachments/assets/83c944ea-074d-4479-a317-bb9556125c96)

![Set your outbound rules](https://github.com/user-attachments/assets/cb225703-b8fe-41fd-8b30-8bf3f7c3932b)

![Created security group](https://github.com/user-attachments/assets/c2f75d23-4b55-48e1-8eef-a5f6c4a89f14)












### 2.2 Create VPC
![Create VPC](https://github.com/user-attachments/assets/d3a9ae6b-e881-4362-bbbb-af9d7803ce1d)
*Define the CIDR block and other configurations to create a custom VPC.*

### 2.3. Configure VPC
![Configure VPC](https://github.com/user-attachments/assets/bda10683-6e7f-49fa-a1d6-b667cc2b9aaa)
*Modify VPC settings such as DNS hostnames and tenancy.*

### 2.4. Create Subnets
![Create Subnet](https://github.com/user-attachments/assets/01c4215d-38f2-491d-b64c-31a6f4680ed2)
*Add public and private subnets within your VPC.*

![Subnet Created](https://github.com/user-attachments/assets/10a4477b-e7c1-4e2f-acae-4e4465f587f4)
*Successful subnet creation confirmation.*

### 2.5. Set Up Internet Gateway
![Create Internet Gateway](https://github.com/user-attachments/assets/1d7edf2b-7fd7-4a0b-827c-02baef3274dc)
*Provision an Internet Gateway for external communication.*

![Attach Internet Gateway](https://github.com/user-attachments/assets/b9b9d9c3-dc26-4436-b188-0d2ad8d586a6)
*Attach the IGW to your VPC to enable internet access.*

### 2.6. Configure Route Tables
![Route Table](https://github.com/user-attachments/assets/f60c8df0-3afd-4b81-8ece-a5dc76baa4a0)
*Set up route tables to control network traffic.*

![Edit Routes](https://github.com/user-attachments/assets/2d81aa2f-82b7-4f60-a734-c72f8f6cfbb1)
*Modify route tables to direct internet-bound traffic through IGW.*

### 2.7. Set Up NAT Gateway
![Create NAT Gateway](https://github.com/user-attachments/assets/cd3be463-0464-443d-8edf-1b8bc82918b8)
*Deploy a NAT Gateway to allow private subnet instances to reach the internet.*

![Add NAT Gateway to Route Table](https://github.com/user-attachments/assets/49af1a84-55d5-4229-ab44-1ae1dadb4030)
*Update route tables to enable NAT Gateway functionality.*

### 2.8. VPC Peering
![Create VPC Peering](https://github.com/user-attachments/assets/a5146609-256e-4f1b-af4d-bcf5544b9a76)
*Establish a VPC Peering connection for inter-VPC communication.*

![Accept Peering Request](https://github.com/user-attachments/assets/fde028d0-f948-4a2a-b7a0-b1658310afe9)
*Approve the peering request from the peer VPC.*

![Edit Peering Route Table](https://github.com/user-attachments/assets/7b2b5e93-75c4-43aa-9a2a-0df4b809f256)
*Update route tables to direct traffic through the peering connection.*

---

## 3. Troubleshooting (Common Issues and Solutions)

### 3.1. VPC Not Connecting to Internet
**Issue:** Instances in the VPC cannot access the internet.
**Solution:**
- Ensure an Internet Gateway is attached.
- Verify route tables include a route to `0.0.0.0/0` via the Internet Gateway.

### 3.2. Subnet Routing Issues
**Issue:** Private instances are not communicating with public instances.
**Solution:**
- Confirm that the route table for private subnets has a NAT Gateway route.
- Ensure the correct subnet associations are applied.

