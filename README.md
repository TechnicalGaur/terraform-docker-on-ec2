
# 🚀 Terraform Docker on AWS EC2

This project demonstrates how to use **Terraform** to deploy a **Docker container** (NGINX) on an **AWS EC2 instance**. The EC2 acts as a local host where Docker is installed and Terraform provisions a container running NGINX, accessible over the internet.

---

## 🧰 Tools & Technologies

- 🌩️ **Terraform**
- 🐳 **Docker**
- 🖥️ **AWS EC2 (Ubuntu or Amazon Linux)**
- 🐙 **Git & GitHub**

---

## 📁 Project Structure

```
terraform-docker-ec2/
├── main.tf               # Terraform configuration file
├── terraform.tfstate     # Terraform state file (auto-generated)
├── .terraform/           # Terraform plugin cache (auto-generated)
```

---

## ⚙️ Prerequisites

Ensure the following are installed on your EC2 instance:

- Terraform (`>= 1.0`)
- Docker Engine
- Git

> ⚠️ Make sure your EC2 security group allows **port 8080** (for NGINX access) and **port 22** (for SSH).

---

## 🔨 Setup & Deployment

### 1. 🔄 Initialize Terraform

```bash
terraform init
```

### 2. 🔍 Preview the Plan

```bash
terraform plan
```

### 3. 🚀 Apply the Configuration

```bash
terraform apply
```

Type `yes` when prompted.

Once complete, NGINX will be running on:

```
http://<your-ec2-public-ip>:8080
```

> Use `docker ps` to verify the running container.

---

## 🧼 Destroy Resources

To remove the Docker container:

```bash
terraform destroy
```

---

## 📦 Docker Resources Used

- **Image:** nginx:latest
- **Container Name:** nginx-server
- **Ports:** 8080 (external) → 80 (internal NGINX)

---

## 📌 Notes

- Uses `kreuzwerker/docker` Terraform provider
- Docker provider connects to local Docker daemon via Unix socket: `unix:///var/run/docker.sock`
- Terraform manages image pull and container creation lifecycle

---

## 📡 GitHub Setup

### 1. Initialize Git & Commit

```bash
git init
git add .
git commit -m "Terraform Docker on EC2"
```

### 2. Push to GitHub

```bash
git remote add origin https://github.com/<your-username>/terraform-docker-on-ec2.git
git push -u origin main
```

> Use a **GitHub token** instead of password: [Create Token](https://github.com/settings/tokens)

---

## 🙋‍♂️ Author

**Prashant Gour**  
🔗 [GitHub](https://github.com/TechnicalGaur)

---

## 📄 License

This project is open-source and free to use under the [MIT License](LICENSE).
---

## Screenshot


<img width="1352" height="684" alt="Screenshot 2025-08-07 124322" src="https://github.com/user-attachments/assets/b150a327-aad0-439e-8a70-2d5694154a64" />



<img width="1340" height="675" alt="Screenshot 2025-08-07 121125" src="https://github.com/user-attachments/assets/327b42d8-1646-4356-9f81-46137eb1cbb0" />



<img width="1314" height="709" alt="Screenshot 2025-08-07 120800" src="https://github.com/user-attachments/assets/5e23400e-795d-4917-8a40-b2d2290cac5c" />



<img width="1334" height="726" alt="Screenshot 2025-08-07 124349" src="https://github.com/user-attachments/assets/bd1394f6-1f5c-46e6-bf89-c35bc6a2ba83" />



