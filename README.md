# Homelab Kubernetes Services 🚀

![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white) ![ArgoCD](https://img.shields.io/badge/ArgoCD-3E7BFA?style=for-the-badge&logo=argocd&logoColor=white) ![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white) ![Prometheus](https://img.shields.io/badge/Prometheus-EC7F3A?style=for-the-badge&logo=prometheus&logoColor=white)

Welcome to the **Homelab Kubernetes Services** repository! This project provides production-ready Kubernetes configurations tailored for self-hosted services in homelab environments. Whether you're looking to set up monitoring, CI/CD pipelines, or other services, you’ll find the necessary configurations here.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Configuration](#configuration)
- [Monitoring](#monitoring)
- [Deploying Services](#deploying-services)
- [Contributing](#contributing)
- [License](#license)
- [Releases](#releases)

## Introduction

In a world where cloud services dominate, self-hosting offers flexibility and control. This repository aims to provide a robust framework for deploying services in your homelab using Kubernetes. You can easily adapt the configurations to suit your needs.

## Features

- **Production-ready Configurations**: All configurations are tested and ready for production use.
- **Easy Deployment**: Simplified deployment processes using Helm and Kustomize.
- **Monitoring Tools**: Built-in support for Grafana and Prometheus to keep an eye on your services.
- **CI/CD Integration**: Seamless integration with ArgoCD and Flux for GitOps workflows.
- **SSL Management**: Use Cert-Manager for automatic SSL certificate provisioning.
- **Load Balancing**: Leverage MetalLB for load balancing in your homelab.

## Technologies Used

This repository includes configurations for various tools and technologies:

- **Kubernetes**: The core platform for container orchestration.
- **Helm**: A package manager for Kubernetes.
- **Kustomize**: A tool for customizing Kubernetes YAML configurations.
- **ArgoCD**: A declarative, GitOps continuous delivery tool for Kubernetes.
- **Flux**: Another GitOps tool for managing Kubernetes resources.
- **Cert-Manager**: A tool for managing SSL certificates.
- **Grafana**: A visualization tool for monitoring.
- **Prometheus**: A powerful monitoring and alerting toolkit.
- **Ingress-NGINX**: A robust ingress controller for Kubernetes.
- **MetalLB**: A load balancer implementation for bare metal Kubernetes clusters.

## Getting Started

To get started with the Homelab Kubernetes Services, follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Galiwango001/homelab-k8s-services.git
   cd homelab-k8s-services
   ```

2. **Install Required Tools**:
   Ensure you have the following tools installed:
   - `kubectl`
   - `helm`
   - `kustomize`
   - `argocd` (if using ArgoCD)
   - `flux` (if using Flux)

3. **Set Up Your Kubernetes Cluster**:
   You can use any Kubernetes provider, such as Minikube, GKE, or EKS. Ensure your cluster is up and running.

## Usage

To use the configurations in this repository, navigate to the specific service you want to deploy. Each service folder contains a `README.md` file with detailed instructions.

### Example: Deploying Grafana

1. **Navigate to the Grafana Directory**:
   ```bash
   cd grafana
   ```

2. **Deploy Using Helm**:
   ```bash
   helm install grafana ./grafana
   ```

3. **Access Grafana**:
   Follow the instructions in the `README.md` file to access the Grafana dashboard.

## Configuration

Each service has its own configuration files. You can customize these files based on your requirements. The configurations typically include:

- **Deployment YAML**: Defines the deployment settings for the service.
- **Service YAML**: Specifies how the service is exposed.
- **Ingress YAML**: Manages the ingress routing for the service.

### Example Configuration for Ingress

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: example-ingress
spec:
  rules:
  - host: example.local
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: example-service
            port:
              number: 80
```

## Monitoring

Monitoring is crucial for maintaining the health of your services. This repository includes configurations for Prometheus and Grafana. 

### Setting Up Prometheus

1. **Navigate to the Prometheus Directory**:
   ```bash
   cd prometheus
   ```

2. **Deploy Prometheus**:
   ```bash
   helm install prometheus ./prometheus
   ```

3. **Access Prometheus**:
   Follow the instructions in the `README.md` file to access the Prometheus dashboard.

## Deploying Services

You can deploy multiple services using the configurations provided. Each service is modular and can be deployed independently.

### Example: Deploying a Web Application

1. **Navigate to the Web Application Directory**:
   ```bash
   cd web-app
   ```

2. **Deploy the Application**:
   ```bash
   kubectl apply -f deployment.yaml
   ```

3. **Check the Status**:
   ```bash
   kubectl get pods
   ```

## Contributing

Contributions are welcome! If you have suggestions or improvements, feel free to open an issue or submit a pull request. Please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or fix.
3. Commit your changes.
4. Push to your forked repository.
5. Create a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Releases

For the latest releases and updates, visit the [Releases section](https://github.com/Galiwango001/homelab-k8s-services/releases). Download the necessary files and execute them to set up your services.

You can also check the [Releases section](https://github.com/Galiwango001/homelab-k8s-services/releases) for any updates or changes.

## Conclusion

The Homelab Kubernetes Services repository aims to simplify the process of deploying self-hosted services in a Kubernetes environment. With easy-to-follow configurations and a focus on production readiness, you can take full control of your homelab.

Feel free to explore the various services, customize them to your needs, and contribute to the project. Happy hosting!