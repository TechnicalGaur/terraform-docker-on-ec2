
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

