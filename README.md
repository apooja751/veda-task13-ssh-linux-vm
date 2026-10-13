# Task 13 — Connect to a Cloud VM Using SSH

## Cloud Computing Internship — Veda Technology

### 1. Objective

To connect securely to a cloud-based Linux virtual machine using SSH and perform basic Linux system administration commands.

### 2. Tools and Technologies

- **Cloud Provider:** Amazon Web Services (AWS)
- **Cloud Service:** Amazon EC2
- **Operating System:** Ubuntu Server 26.04 LTS
- **Instance Type:** `t3.micro`
- **Storage:** 8 GiB EBS root volume (`gp3`)
- **Remote Access:** SSH
- **Terminal:** Windows PowerShell
- **Authentication:** SSH key pair

### 3. Instance Configuration

An Ubuntu EC2 instance named `veda-task13-ssh-vm` was launched in the AWS Asia Pacific (Mumbai) Region.

The instance was configured with a public IPv4 address and a security group allowing SSH access on TCP port 22 from my IP address.

The SSH key pair `veda-key` was used for authentication. The private key was kept on the local machine and was not uploaded to GitHub.

### 4. Procedure

1. Opened the AWS Management Console and navigated to Amazon EC2.
2. Selected Ubuntu Server 26.04 LTS as the Amazon Machine Image.
3. Selected the `t3.micro` instance type.
4. Configured the existing default VPC, enabled public IPv4 assignment, and created a security group.
5. Restricted inbound SSH access to my IP address on TCP port 22.
6. Configured an 8 GiB `gp3` root volume.
7. Launched the EC2 instance and verified that it was running.
8. Connected to the Ubuntu instance from Windows PowerShell using SSH and the private key.
9. Executed basic Linux commands to verify the hostname, logged-in user, uptime, disk space, and memory usage.

### 5. SSH Connection

The following command was used to connect to the Ubuntu instance:

```bash
ssh -i "C:\Users\user\Downloads\veda-key.pem" ubuntu@<EC2-PUBLIC-DNS>
```

Replace `<EC2-PUBLIC-DNS>` with the public DNS name of the instance.

The connection was successful, and the Ubuntu terminal prompt was displayed.

### 6. Linux Commands and Results

| Command | Purpose | Observed result |
|---|---|---|
| `hostname` | Displays the system hostname | `ip-172-31-4-156` |
| `whoami` | Displays the current user | `ubuntu` |
| `uptime` | Displays uptime and system load | Approximately 13 minutes during the check |
| `df -h` | Displays disk space in a readable format | Root filesystem: 6.7 GiB, 31% used |
| `free -m` | Displays memory usage in MB | 908 MB total, 304 MB used, 604 MB available |

The results above were observed during the practical execution. Uptime and resource usage can change over time.

### 7. Screenshots and Evidence

The `Screenshots` folder contains evidence of the following stages:

1. Instance configuration
2. Instance type and key pair
3. Network and security settings
4. Storage configuration
5. Running EC2 instance
6. Storage verification
7. Successful SSH connection
8. Hostname and current user
9. Uptime and disk space
10. Memory usage

### 8. Security Considerations

- SSH access was restricted to my IP address.
- SSH key-based authentication was used.
- The private key file was not uploaded to the repository.
- AWS credentials and other secrets must not be committed to GitHub.
- The SSH security group rule should be updated if the public IP address changes.

### 9. Outcome

Successfully launched an Ubuntu virtual machine on AWS EC2, connected to it remotely using SSH, and executed basic Linux administration commands to inspect system identity, uptime, disk space, and memory usage.

### 10. Conclusion

This practical demonstrated the basic process of provisioning a Linux virtual machine in the cloud, configuring secure remote access, and using Linux commands to inspect system resources. These skills are foundational for Linux system administration and cloud infrastructure management.
