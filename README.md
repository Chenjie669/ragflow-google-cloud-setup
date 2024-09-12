# ragflow-google-cloud-setup
Guide to Installing Ragflow on Google Cloud Compute Engine
# Installing Ragflow on Google Cloud Compute Engine

This guide walks you through the process of setting up Ragflow on a Google Cloud Compute Engine virtual machine (VM). It covers deploying the llama3.1:70b model using Ollama on the VM and configuring Ragflow to work with locally deployed models.

## Prerequisites

- **Google Cloud Account**: Ensure you have access to Google Cloud and the Compute Engine service. New accounts typically come with approximately $440 in free credits.
- **Compute Engine Setup**: You'll need a VM with at least 4 CPUs (equivalent to 8 vCPUs), 16 GB of memory, and 50 GB of disk space to run Ragflow. If you're planning to run the llama3.1:70b model, I recommend using about 80 GB of memory and 10 cores (20 vCPUs), as the model requires at least 40 GB of memory. You'll also need around 100 GB of storage (since llama3.1:70b itself is around 40 GB), though these settings can be adjusted later.
- **Docker**: Docker needs to be installed on the VM to run Ragflow.

## Steps

### 1. Set Up Google Cloud Compute Engine

- **Create a new VM instance** in the Google Cloud Console. Choose a machine type with the required resources (e.g., n2-standard-4).
- **Configure firewall rules** to allow traffic on the necessary ports (e.g., 11434 for Ollama).

### 2. Install Docker on the VM

SSH into your VM and run the following commands to install Docker:

```bash
sudo apt-get update
sudo apt-get install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
