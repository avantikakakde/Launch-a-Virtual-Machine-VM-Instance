# Launch-a-Virtual-Machine-VM-Instance


### 1. Log in to AWS Management Console

- Go to [https://aws.amazon.com/console/](https://aws.amazon.com/console/) and sign in.

### 2. Navigate to EC2 Dashboard

- Search for **EC2** in the AWS services search bar and open the EC2 dashboard.

![](./images/Screenshot%202025-10-22%20123326.png)





### 3 . Launch a New EC2 Instance

- Click **Instances** in the left sidebar.
- Click **Launch Instances**.

![](./images/Screenshot%202025-10-22%20123343.png)

- Select an Amazon Machine Image (AMI) (e.g., **Ubuntu Server**).

![](./images/Screenshot%202025-10-22%20123517.png)

- Choose an instance type (e.g., `t2.micro` — free tier eligible).

![](./images/Screenshot%202025-10-22%20123610.png)

- Click **Next: Configure Instance Details** — usually defaults are fine.
- Click **Next: Add Storage** — keep defaults or increase if needed.
- Click **Next: Add Tags** — optional tags for organization.
- Click **Next: Configure Security Group**:
  - Add a rule to allow **SSH (port 22)** from your IP address:
    - Type: SSH
    - Protocol: TCP
    - Port Range: 22
    - Source: My IP (recommended for security)

![](./images/Screenshot%202025-10-22%20123940.png)

![](.)



### 4. Create a Key Pair (SSH Key)

- In the left sidebar, click on **Key Pairs** under **Network & Security**.
- Click **Create Key Pair**.
- Provide a name (e.g., `my-ec2-key`).
- Select the key type as **RSA** (default).
- Click **Create key pair**.
- The private key file (`.pem`) will be downloaded automatically. Keep this file safe — you will need it to SSH into your server.
- Click **Review and Launch**.
- Click **Launch**.
- Select the key pair you created earlier (e.g., `my-ec2-key`).
- Check the acknowledgment box and click **Launch Instances**.

![](./images/Screenshot%202025-10-22%20124035.png)

### 5. Connect to Your EC2 Instance Using SSH

- Wait for the instance state to be **running**.
- Get the **Public IPv4 address** 
- Open your terminal and run:

ssh -i /path/to/my-ec2-key.pem ec2-user@your-ec2-public-ip

![](./images/Screenshot%202025-10-22%20125701.png)

##  6: Test Connection

- Run basic Linux commands:

 Test Connection


```bash
uname -a
ls
whoami
```


![](./images/Screenshot%202025-10-22%20125821.png)

