# Installing AWS Linux 🚀

## Table of Contents
- Prerequisites
- Creating an AWS Account
- Launching an EC2 Instance
- Connecting to Your Instance
- Basic Setup and Configuration
- Best Practices
- Troubleshooting

## Prerequisites 📝
- AWS Account
- Basic understanding of Linux commands
- SSH client (PuTTY for Windows or Terminal for Mac/Linux)
- Key pair for SSH access

## Creating an AWS Account 🔐
1. Visit aws.amazon.com
2. Click "Create an AWS Account"
3. Follow the registration process
4. Set up billing alerts (recommended)

## Launching an EC2 Instance 🖥️
1. Log in to AWS Console
2. Navigate to EC2 Dashboard
3. Click "Launch Instance"
4. Choose Amazon Linux 2 AMI
5. Select instance type (t2.micro is free tier eligible)
6. Configure Instance Details:
   - Keep default VPC settings
   - Enable auto-assign public IP
7. Add Storage (default 8GB is usually sufficient)
8. Add Tags (optional but recommended):
   - Key: Name
   - Value: MyLinuxServer
9. Configure Security Group:
   - Allow SSH (Port 22)
   - Allow HTTP (Port 80) if needed
   - Allow HTTPS (Port 443) if needed
10. Review and Launch
11. Select/create key pair
12. Launch Instance

## Connecting to Your Instance 🔌
### For Windows Users:
1. Open PuTTY
2. Enter your instance's public IP
3. Configure SSH key
4. Connect using: ec2-user@your-instance-ip

### For Mac/Linux Users:
```bash
chmod 400 your-key.pem
ssh -i your-key.pem ec2-user@your-instance-ip
```

## Basic Setup and Configuration ⚙️
1. Update system packages:
```bash
sudo yum update -y
```

2. Install common tools:
```bash
sudo yum install -y wget htop vim
```

3. Configure timezone:
```bash
sudo timedatectl set-timezone YOUR_TIMEZONE
```

## Best Practices 🎯
1. Security:
   - Use strong passwords
   - Keep system updated
   - Use Security Groups effectively
   - Implement proper firewall rules

2. Maintenance:
   - Regular backups
   - Monitor resources
   - Set up CloudWatch alerts

3. Cost Management:
   - Use free tier when possible
   - Stop instances when not in use
   - Monitor AWS billing

## Troubleshooting 🔧
Common Issues and Solutions:

1. Cannot Connect:
   - Check security group settings
   - Verify key pair permissions
   - Confirm instance is running

2. Slow Performance:
   - Check CPU usage
   - Monitor memory usage
   - Verify instance type is appropriate

3. Storage Issues:
   - Monitor disk usage
   - Clean up unnecessary files
   - Consider expanding volume

## Useful Commands 💻
```bash
# Check system resources
top
df -h
free -m

# Monitor logs
tail -f /var/log/messages

# Network connectivity
netstat -tulpn
```

## Additional Resources 📚
- [AWS Documentation](https://docs.aws.amazon.com)
- [Amazon Linux 2 User Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/amazon-linux-2-virtual-machine.html)
- [AWS CLI Documentation](https://aws.amazon.com/cli/)

---
🔑 Remember to:
- Always backup important data
- Follow security best practices
- Keep your system updated
- Monitor your AWS costs

Last Updated: July 2025
