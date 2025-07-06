# 𝙃𝙚𝙡𝙡𝙤 𝙄'𝙢 𝘼𝙝𝙢𝙚𝙙 𝙎𝙖𝙡𝙞𝙢! 👨‍💻
#### I'm a passionate DevOps Engineer and Cloud Specialist with expertise in building scalable infrastructure and automating workflows.

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=24&duration=3000&pause=1000&color=00FFFF&center=true&vCenter=true&width=500&lines=DevOps+Engineer;Cloud+Architect;Automation+Specialist" alt="Typing animation" />
</p>

<p align="center">
  <img src="https://techstack-generator.vercel.app/aws-icon.svg" width="50" height="50" alt="AWS" />
  <img src="https://techstack-generator.vercel.app/docker-icon.svg" width="50" height="50" alt="Docker" />
  <img src="https://techstack-generator.vercel.app/kubernetes-icon.svg" width="50" height="50" alt="Kubernetes" />

## 📊 GitHub Stats
<p align="center">
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=ahmed7100&show_icons=true&theme=dark&include_all_commits=true&count_private=true&bg_color=000000&title_color=00ffff&text_color=ffffff&icon_color=00ffff" />
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=ahmed7100&layout=compact&langs_count=6&theme=dark&bg_color=000000&title_color=00ffff&text_color=ffffff&hide=Jupyter%20Notebook" />
</p>
<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=ahmed7100&theme=black-ice&background=000000&stroke=00ffff&ring=00ffff&fire=00ffff&currStreakNum=ffffff&sideNums=ffffff&currStreakLabel=ffffff&sideLabels=ffffff&dates=ffffff" />
</p>

## 🚀 Featured Projects

### [Infrastructure Automation Toolkit](https://github.com/ahmed7100/infra-automation)
🚀 End-to-End DevOps Kubernetes Three-Tier Project using AWS EKS, Docker, ArgoCD, Prometheus, Grafana, and Github Actions.

![Screenshot 2025-07-04 174131.png](attachment:f7b14e33-7c65-46ac-bd98-a3d8d3bfeec7:Screenshot_2025-07-04_174131.png)

# **Project Introduction:**

Welcome to the End-to-End DevOps Kubernetes Project guide! In this comprehensive project, I will walk you through the process of setting up a robust Three-Tier architecture on AWS using Kubernetes, DevOps best practices, and security measures. This project aims to provide hands-on experience in deploying, securing, and monitoring a scalable application environment.

# **Project Overview**

In this project, we will cover the following key aspects:

1. **IAM User Setup**: Create an IAM user with appropriate permissions to manage infrastructure using AWS CLI and Terraform securely.
2. **Self-Hosted Runner Setup**: Configure a GitHub Actions self-hosted runner on EC2.
3. **DNS Management with Namecheap and Route 53**: Configure a domain purchased on Namecheap, and integrate it with Amazon ****Route ****53 for DNS routing and subdomain management.
4. **Terraform State Management**: Use an Amazon ****S3 ****bucket as a remote backend to store and manage the Terraform state file for infrastructure provisioning.
5. **Infrastructure as Code (IaC)**: Provision all required cloud resources, including VPC, subnets, EKS cluster, and RDS using Terraform and  AWS CLI.
6. **Amazon EKS Cluster**: Deploy a highly available managed Kubernetes cluster using `eksctl`, providing the foundation for container orchestration.
7. **Amazon ECR**: Store and manage container images (backend and frontend) in Amazon Elastic Container Registry (ECR).
8. **CI/CD with GitHub Actions**: Automate build, test, and deployment workflows using GitHub ****Actions, pushing container images to ECR and triggering application updates in EKS via ArgoCD.
9. **ArgoCD for GitOps**: Enable continuous deployment by syncing Kubernetes manifests from GitHub repositories to the EKS cluster using ArgoCD.
10. **Application Load Balancer (ALB)**: Use AWS ****ALB to expose services running in EKS securely to the internet.
11. **NGINX Ingress Controller**: Manage internal routing of traffic within the Kubernetes cluster using NGINX ****Ingress, enabling clean URL paths and multi-service ingress rules.
12. **TLS with Let’s Encrypt**: Secure traffic with **free** SSL **certificates** issued and auto-renewed by Let's ****Encrypt, integrated with the NGINX Ingress controller.
13. **Monitoring with Prometheus and Grafana**: Deploy Prometheus and Grafana via Helm to visualize metrics and monitor the health of the cluster and deployed services.
14. **Three-Tier Application Deployment**: Deploy the full application stack (frontend, backend, database) using Kubernetes manifests and Helm, managed via ArgoCD.
15. **Project Completion and Monitoring**: Finalize with a system overview, validate deployments, and continuously monitor using Grafana dashboards.

# **Prerequisites:**

Before starting the project, ensure you have the following prerequisites:

- An AWS account with the necessary permissions to create resources.
- Terraform and AWS CLI installed on your local machine.
- Basic familiarity with Kubernetes, Docker, GitHub Actions, and DevOps principles.

**Step 1: We need to create an IAM user and generate the AWS Access key**

Create a new IAM User on AWS and give it to the *AdministratorAccess* for securely automating your AWS infrastructure and deployment workflows. (not recommended for your Organization's Projects)

Go to the AWS IAM Service and click on **Users.**

![Screenshot 2025-07-04 190129.png](attachment:5c845635-627c-40dc-849e-cedd2d8d0f55:Screenshot_2025-07-04_190129.png)

Click on **Create user**

![Screenshot 2025-07-04 190229.png](attachment:6b99719c-f33e-4145-8106-ad07f27d1c6f:Screenshot_2025-07-04_190229.png)

Provide the name to your user and click on **Next.**

![Screenshot 2025-07-04 190348.png](attachment:c092d158-1369-49ca-8904-2cdac12219ab:Screenshot_2025-07-04_190348.png)

Select the **Attach policies directly** option and search for ***AdministratorAccess*** then select it**.**

Click on the **Next.**

![image.png](attachment:6bd5ef88-aa8f-449e-85d5-f10ac81d4021:image.png)

Click on **Create user**

![Screenshot 2025-07-04 191004.png](attachment:316ae5ba-d7d7-4293-9fab-8c610122f8d4:Screenshot_2025-07-04_191004.png)

Now, Select your created user then click on **Security credentials** and generate access key by clicking on **Create access key.**

![image.png](attachment:8c4632fd-3f2d-4b42-bc09-dd3cd487db7d:image.png)

Select the **Command Line Interface (CLI)** then select the checkmark for the confirmation and click on **Next.**

![Screenshot 2025-07-04 191407.png](attachment:e0f4cbc1-2af8-4142-87bf-e6a299f97a9d:Screenshot_2025-07-04_191407.png)

Provide the **Description** and click on the **Create access key.**

![Screenshot 2025-07-04 191710.png](attachment:0cf8f6ad-9330-4996-a49e-c5f84d0bf1fa:Screenshot_2025-07-04_191710.png)

Here, you will see that you got the credentials and also you can download the CSV file for the future.

![Screenshot 2025-07-04 191847.png](attachment:757dc58c-7ae6-445b-b380-cdae4c8b2fa3:Screenshot_2025-07-04_191847.png)

**Step 2: We will set Up a Self-Hosted GitHub Actions Runner on an EC2 Instance.**

In this step, we will create and configure a self-hosted GitHub Actions runner on an EC2 instance. This runner will be used to execute GitHub Actions workflows within your infrastructure, giving you more control, better performance, and the ability to interact securely with your private AWS resources such as EKS, RDS, and ECR.

Go to the **AWS Management Console**. Search for EC2 and Launch a new EC2 instance.

![image.png](attachment:07354be4-47ea-43f5-8247-402e53d6fbfa:image.png)

Provide the name to your instance and choose Ubuntu OS ****Images.

![Screenshot 2025-07-04 194002.png](attachment:7eedc985-ea24-43f2-ac2d-8976cfd3552f:Screenshot_2025-07-04_194002.png)

For the instance type, choose *t2.medium* and Assign a key ****pair for SSH access or create one.

![Screenshot 2025-07-04 194925.png](attachment:ebcb016f-06a5-4d44-a2c6-50e57ec9463b:Screenshot_2025-07-04_194925.png)

Place the instance in the **correct** VPC **and** subnet. Allow inbound traffic on port 22 **(**SSH**)** and ****set ****CIDR ****block ****to ****0.0.0.0/0.

![Screenshot 2025-07-04 195525.png](attachment:a744c649-16a1-4656-996b-4103248c68a7:Screenshot_2025-07-04_195525.png)

Set the storage to 10GB.

![Screenshot 2025-07-04 195803.png](attachment:8eff2d5c-51e7-4f60-8467-c1228d097162:Screenshot_2025-07-04_195803.png)

Launch your EC2 Instance.

![image.png](attachment:7edbed41-060e-4961-b7db-112e24aa87d2:image.png)

Select the Instance and connect to the Instance.

![image.png](attachment:fce9e4fb-6dbb-4ce9-bbdd-2f03470bb6ec:image.png)

Now, click on connect.

![Screenshot 2025-07-04 200545.png](attachment:2aa652ef-16ae-41d6-968f-8dac5c109492:Screenshot_2025-07-04_200545.png)

Once on your terminal,  run the following command.

```bash
sudo apt update && sudo apt install docker.io docker-compose -y
```

- `sudo apt update` updates the system's package list.
- `sudo apt install docker.io docker-compose` installs Docker Engine and Docker Compose.
- `y` auto-confirms prompts during installation.

![Screenshot 2025-07-05 063145.png](attachment:f0423429-2b39-4b08-ad78-ff91377f7a8c:Screenshot_2025-07-05_063145.png)

Once the installation is over, confirm that docker and docker-compose is installed by running the following commands.

```bash
docker --version            # For docker.

docker-compose --version    # For docker-compose.
```

![image.png](attachment:d9712a58-f894-4ec1-bc6d-675697aeedb3:image.png)

Now that Docker and docker-compose are installed, create the runner directory.

```bash
mkdir runner && cd runner
```

![Screenshot 2025-07-05 070647.png](attachment:176ae5b4-9961-4449-8bf8-3961ae8d8a66:Screenshot_2025-07-05_070647.png)

Now create the required files Inside the `runner` folder, create the following:

- `.env` – Stores environment variables.
- `Dockerfile` – Defines the container environment.
- `docker-compose.yaml` – Orchestrates the runner container.
- `entrypoint.sh` – Bootstraps the runner on container start.

![Screenshot 2025-07-05 072721.png](attachment:6401d571-c0c0-419d-a7cf-4da994b629bd:Screenshot_2025-07-05_072721.png)

.env 

```bash
GITHUB_PAT=ghp_XXXXXXXXN0JJrRv6uIVn1SK9eaVnN054Ufq
REPO=Ahmed7100/bankapp-infrastructure 
RUNNER_NAME=self-hosted-runner
```

Dockerfile

```docker
FROM ubuntu:22.04

# Avoid interactive prompts during install
ENV DEBIAN_FRONTEND=noninteractive

# Install dependencies
RUN apt-get update && apt-get install -y \
    curl \
    git \
    jq \
    unzip \
    docker.io \
    sudo \
    software-properties-common \
    gnupg \
    lsb-release \
    ca-certificates \
    nodejs \
    npm && \
    rm -rf /var/lib/apt/lists/*

# Install Terraform
RUN curl -fsSL https://apt.releases.hashicorp.com/gpg | gpg --dearmor -o /usr/share/keyrings/hashicorp.gpg && \
    echo "deb [signed-by=/usr/share/keyrings/hashicorp.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" \
    > /etc/apt/sources.list.d/hashicorp.list && \
    apt-get update && apt-get install -y terraform

# Create a non-root user for the runner
RUN useradd -m -s /bin/bash runner && \
    usermod -aG docker runner && \
    echo "runner ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

# Set working directory
WORKDIR /home/runner

# Download and extract the GitHub Actions runner
RUN curl -s https://api.github.com/repos/actions/runner/releases/latest \
  | jq -r '.assets[] | select(.name | test("linux-x64")) | .browser_download_url' \
  | xargs curl -LO && \
  tar xzf actions-runner-linux-x64-*.tar.gz && \
  rm actions-runner-linux-x64-*.tar.gz

# Copy entrypoint script
COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh && chown -R runner:runner /home/runner

# Ensure correct permissions
RUN mkdir -p /home/runner/_work && chown -R runner:runner /home/runner

# Switch to non-root user
USER runner

# Start the GitHub runner
ENTRYPOINT ["/entrypoint.sh"]
```

docker-compose.yaml

```yaml
version: "3.8"

services:
  github-runner:
    build:
      context: .
      dockerfile: Dockerfile
    image: docker-runner:latest
    container_name: github-runner
    restart: unless-stopped
    env_file:
      - .env
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - runner-work:/home/runner/_work

volumes:
  runner-work:
```

entrypoint.sh

```bash
version: "3.8"

services:
  github-runner:
    build:
      context: .
      dockerfile: Dockerfile
    image: docker-runner:latest
    container_name: github-runner
    restart: unless-stopped
    env_file:
      - .env
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - runner-work:/home/runner/_work

volumes:
  runner-work:
ubuntu@ip-172-31-24-156:~/runner$ cat entrypoint.sh 
#!/bin/bash
set -e

cd /home/runner

echo "[INFO] Fixing permissions for /home/runner/_work..."
mkdir -p /home/runner/_work
chown -R runner:runner /home/runner/_work

# Check for required environment variables
if [[ -z "$REPO" || -z "$GITHUB_PAT" || -z "$RUNNER_NAME" ]]; then
  echo "[ERROR] Required environment variables REPO, GITHUB_PAT, or RUNNER_NAME are missing."
  exit 1
fi

# Request a registration token
TOKEN_URL="https://api.github.com/repos/${REPO}/actions/runners/registration-token"
echo "[INFO] Requesting registration token for $REPO..."

RUNNER_TOKEN=$(curl -s -X POST \
  -H "Authorization: token ${GITHUB_PAT}" \
  "${TOKEN_URL}" | jq -r .token)

# Check if token was retrieved successfully
if [[ -z "$RUNNER_TOKEN" || "$RUNNER_TOKEN" == "null" ]]; then
  echo "[ERROR] Failed to retrieve runner token. Check if your GITHUB_PAT is valid and has repo/admin access."
  exit 1
fi

echo "[INFO] Registering runner: $RUNNER_NAME"
./config.sh --unattended \
  --url "https://github.com/${REPO}" \
  --token "${RUNNER_TOKEN}" \
  --name "${RUNNER_NAME}" \
  --labels self-hosted,docker,terraform \
  --work _work \
  --replace

echo "[INFO] Starting runner..."
exec ./run.sh
```

Build and run the container.

```bash
docker-compose up -d --build
```

Now, you should have your container built and running.

![Screenshot 2025-07-05 074749.png](attachment:5457c5b1-f0d5-43e3-8c2c-661b4455b7fa:Screenshot_2025-07-05_074749.png)

check to see if container is running.

```bash
 docker ps
```

If it’s running, you should get the following output.

![Screenshot 2025-07-05 083116.png](attachment:89590d94-653f-4009-b621-759eba19cae3:Screenshot_2025-07-05_083116.png)

Also check for the logs to ensure that your self-hosted runner connection is good.

```bash
docker logs github-runner
```

You should get the following output.

![Screenshot 2025-07-05 082611.png](attachment:0cf1867a-8c5b-42bf-a231-b84441d65d44:Screenshot_2025-07-05_082611.png)

To verify in GitHub:

Go to Repository **→** Settings **→** Actions **→** Runners.

![image.png](attachment:ba3112ed-160e-408f-92c5-0010eb4b887b:image.png)

The runner ****shows **"**Idle**"** because it’s successfully registered and waiting for a workflow to run. This is normal ****behaviour.

It means:

- The runner is online and ready.
- No GitHub Actions jobs are currently running.

Once a workflow that targets this runner is triggered, its status will change to **"**Running**"**.

### Step3: We will register Domain on Namecheap & Delegate to Route 53.

We’re registering a custom domain for our project and setting up subdomains for our backend API and ArgoCD dashboard. We’ll also create a support email and point the domain to Route 53 for DNS management.

Go to [namecheap.com](https://namecheap.com/)

Search and purchase your desired domain

![image.png](attachment:8e213bca-5d54-4c30-a77a-e499079c36ea:image.png)

Set up two subdomains:

- `api.yourdomain.com` (for the backend)
- `argocd.yourdomain.com` (for ArgoCD dashboard)

Now create a professional email (e.g., `support@yourdomain.com`) using Namecheap ****Private ****Email and connect it to your domain for sending and receiving email.

![Project Screenshot](https://via.placeholder.com/400x200/000000/00ffff?text=Infra+Automation)

### [CI/CD Pipeline Template](https://github.com/ahmed7100/cicd-pipeline)
⚡ GitHub Actions workflow with ArgoCD integration for Kubernetes deployments

![Project Screenshot](https://via.placeholder.com/400x200/000000/00ffff?text=CI/CD+Pipeline)

## 🛠 Tech Stack

### ☁️ Cloud Platforms
<p align="left">
<img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white" />
<img src="https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white" />
<img src="https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoft-azure&logoColor=white" />
</p>

### ⚙️ DevOps Tools
<p align="left">
<img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white" />
<img src="https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white" />
<img src="https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white" />
<img src="https://img.shields.io/badge/ArgoCD-EF7B4D?style=for-the-badge&logo=argo&logoColor=white" />
<img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white" />
</p>

### 📊 Monitoring
<p align="left">
<img src="https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white" />
<img src="https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white" />
<img src="https://img.shields.io/badge/Elastic-005571?style=for-the-badge&logo=elastic&logoColor=white" />
</p>

### 💻 Languages
<p align="left">
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" />
<img src="https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white" />
<img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" />
<img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" />
</p>

## 📫 Contact Me
<p align="left">
  <a href="ahmedsalimtatahnyuykighan@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
  <a href="https://www.linkedin.com/in/ahmed-salim-124240255">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="https://wa.me/237671003829">
    <img src="https://img.shields.io/badge/Whatsapp-1DA1F2?style=for-the-badge&logo=whatsapp&logoColor=white" />
  </a>
</p>

## 🌟 Visitor Count
![Visitor Count](https://visitor-badge.laobi.icu/badge?page_id=ahmed7100.ahmed7100)

---

<p align="center">
  <img src="https://raw.githubusercontent.com/ahmed7100/ahmed7100/output/github-contribution-grid-snake.svg" alt="Snake animation"/>
</p>

<p align="center"> 
  <i>Let's build something amazing together!</i>
  <br><br>
  <img src="https://img.shields.io/badge/Open_for-Collaboration-00ffff?style=for-the-badge&logo=github" />
</p>
