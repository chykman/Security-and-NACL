# Security-and-NACL


## 2. Project Steps and Commands

### 2.1. Go to Subnet page

- Create subnet
![Create subnet](https://github.com/user-attachments/assets/c72dc682-7dea-4940-9042-758f9c2eca96)

- Enter the details
![Enter the infos](https://github.com/user-attachments/assets/9590de1d-f4aa-495b-a01f-72a72329f5d9)

- Set your inbound rules
![Set your inbound rules](https://github.com/user-attachments/assets/83c944ea-074d-4479-a317-bb9556125c96)

- Set your outbound rules
![Set your outbound rules](https://github.com/user-attachments/assets/cb225703-b8fe-41fd-8b30-8bf3f7c3932b)

- Created security group
![Created security group](https://github.com/user-attachments/assets/c2f75d23-4b55-48e1-8eef-a5f6c4a89f14)


### 2.2. Go to Instance

- Go to your Instance section
![image](https://github.com/user-attachments/assets/be7e17cc-f1f8-4f3e-ae36-dd33724f5e1b)

- Go to change security groups
  ![image](https://github.com/user-attachments/assets/c3b2d3e9-3e9b-4905-ae20-08bf9d1caca7)

- Select your security group and save
    ![image](https://github.com/user-attachments/assets/e0e66897-f901-4d2c-b321-c4c92dba45ed)

  - You can navigate to the open address of the instance on your web browser
    ![image](https://github.com/user-attachments/assets/f9102332-0ef1-49a5-a79d-58923dbea847)






## 3. Testing implications of Security group rules 

### 3.1.  Remove the outbound rule and save
  
![image](https://github.com/user-attachments/assets/6df80520-753d-43ed-8c13-0c31913aa08b)

- Absence of outbound rules still has no effect on traffic from instance to the outside
  ![image](https://github.com/user-attachments/assets/9a25cc4f-7b41-4242-8f51-cefd8aa7457e)

### 3.2.  Remove the inbound rule and save
- Go to the inbound rules and delete and save
    ![image](https://github.com/user-attachments/assets/84c5f198-047a-447c-88fb-c104d203c5b5)

    -Try and access it on the browser
    ![image](https://github.com/user-attachments/assets/f425eb88-767c-470d-95db-d31a2829eb78)

 ### 3.3.  Allow http on outbound rule
 - Go to the outbound rule, add http and save
   ![image](https://github.com/user-attachments/assets/c8e416b3-d381-4a18-bfd2-8995f6f09b01)
   - Inbound rules are empty
     ![image](https://github.com/user-attachments/assets/d0d777e3-075c-4db8-95d6-6ff598975a09)
    -Try and access it on the browser, there is still no access
         ![image](https://github.com/user-attachments/assets/f425eb88-767c-470d-95db-d31a2829eb78)


     ## 4. Testing implications of NACL rules

      - Go and create a NACL
        ![image](https://github.com/user-attachments/assets/1c99b24c-d764-4210-9e81-eaba1e3cbd59)
      -
        ![image](https://github.com/user-attachments/assets/68592e65-b278-4d5a-9200-3ac5ad1962eb)

        - ![image](https://github.com/user-attachments/assets/2e149294-1240-4602-80e2-06c9598aa626)
    
        - Go to the outbound rules
          ![image](https://github.com/user-attachments/assets/0d6113b4-a461-4841-8791-d9ba2922a87a)

          - Make changes to the inbound rules and save
            ![image](https://github.com/user-attachments/assets/ee29fa7d-666f-4c35-a54b-5e5609184686)

            - Goto actions and click on subnet associations
              ![image](https://github.com/user-attachments/assets/988df6de-f4ee-47cd-957b-748d5621c9ad)
             - Select the subnet and save
              ![image](https://github.com/user-attachments/assets/6d1b8875-7496-4add-a27b-7d3383fe1c7f)

           Test your access to the instance,there is still no access cos of the outbound rules are still not allowing traffic
          -![image](https://github.com/user-attachments/assets/2ec9c444-39e0-4112-9133-d95c860af62e)




         





     
















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

