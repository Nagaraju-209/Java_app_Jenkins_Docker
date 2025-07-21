# 🛠️ **Kubernetes ConfigMap Reload with Spring Boot**

This project demonstrates how to dynamically reload configuration in a Spring Boot application using Kubernetes ConfigMaps. It showcases how Kubernetes-native configuration management can be integrated seamlessly into a microservices architecture, enabling changes to be picked up without restarting the application.

## 📘 **About the Project**
This Spring Boot application reads configuration values from a Kubernetes ConfigMap. When the ConfigMap is updated, the application can detect and reload the configuration on-the-fly. This is particularly useful for cloud-native applications that require high availability and minimal downtime.

## 🔧 **Technologies Used**
- Spring Boot  
- Kubernetes  
- ConfigMap & VolumeMounts  
- Docker  
- Maven  
- AWS EKS (or any Kubernetes platform)  

## 🛠️ **Pre-requisites**
- Git  
- Maven  
- Docker  
- Kubernetes Cluster (e.g., AWS EKS)  

## 📥 **Clone the Repository**
```bash
git clone https://github.com/Nagaraju-209/Java_app_Jenkins_Docker.git
cd Java_app_Jenkins_Docker/kubernetes-configmap-reload
```

## 🧪 **Build the Maven Project**
```bash
mvn clean install
```

## 🐳 **Build Docker Image**
```bash
docker build -t dnraju7747/kubernetes-configmap-reload .
```

## 🔐 **DockerHub Login**
```bash
docker login
```

## 📤 **Push Docker Image to DockerHub**
```bash
docker push dnraju7747/kubernetes-configmap-reload
```

## 🚀 **Deploy Application to Kubernetes**
```bash
kubectl apply -f kubernetes-configmap.yml
```

## 📊 **Verify Deployments, Pods, and Services**
```bash
kubectl get deploy
kubectl get pods
kubectl get svc
```

## 🌍 **Access the Application**
Once the LoadBalancer is marked as InService in AWS (or your cloud provider), open the DNS address in your browser:

```text
http://<loadbalancer-dns>:8080/home/data
```

(Replace `<loadbalancer-dns>` with your actual LoadBalancer DNS name)

## 🧹 **Cleanup Kubernetes Resources**
```bash
kubectl delete deploy kubernetes-configmap-reload
kubectl delete svc kubernetes-configmap-reload
```

## 📂 **GitHub Repository**
🔗 https://github.com/Nagaraju-209/Java_app_Jenkins_Docker

## 🐳 **DockerHub Image**
🔗 https://hub.docker.com/r/dnraju7747/kubernetes-configmap-reload

## 📝 **Notes**
- Make sure your Kubernetes nodes have access to pull images from DockerHub.  
- Ensure your kubeconfig is set correctly and points to the active EKS cluster.  
- To enable automatic config refresh, additional setup such as Spring Cloud Kubernetes Config Watcher may be required depending on the Spring Boot version.
