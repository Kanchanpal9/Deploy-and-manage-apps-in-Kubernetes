Objective
Deploy and manage a containerized app on Kubernetes using Minikube.

Tools Required

 Minikube

 kubectl

 Docker 

 Step 1: Install kubectl
 
    curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
    
    chmod +x kubectl
    
    sudo mv kubectl /usr/local/bin/

 Step 2: Install & Start Minikube(Ubuntu)
 
    curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
    
    sudo install minikube-linux-amd64 /usr/local/bin/minikube
    
    minikube start

 Step 3: Install Docker
 
    sudo apt install docker.io -y
    
    sudo usermod -aG docker $USER 
    
    newgrp docker

![Screenshot 2025-05-21 100551](https://github.com/user-attachments/assets/c31313c6-2a84-4bfc-9959-57d633cb1157)


Step 4:Start Minikube (with Docker driver):

   minikube start --driver=docker

 ![Screenshot 2025-05-21 102949](https://github.com/user-attachments/assets/b60ae36d-907d-4442-9963-254d3489b4b2)
  
Step 5: Create deployment.yaml
Step 6: Create service.yaml

![Screenshot 2025-05-21 103812](https://github.com/user-attachments/assets/5d8ff669-91d6-4ff3-be6a-9f93518d1a6b)


Step 7: kubectl apply -f deployment.yaml
Step 8: kubectl apply -f service.yaml

Step 9: Verify Pods & Services
  Check Pods:
    kubectl get pods
    
![Screenshot 2025-05-21 103040](https://github.com/user-attachments/assets/6625a3b3-2ef2-4104-8c6f-0f93a6fc75ea)

  Check Services:
    kubectl get services
    
![Screenshot 2025-05-21 1040192](https://github.com/user-attachments/assets/9755b5c1-4049-45df-abc2-ddad05a1f628)

Step 10: Scale the Deployment

   kubectl scale deployment nginx-deployment --replicas=4
   
 Verify Scaling:
     kubectl get pods

![Screenshot 2025-05-21 1040191](https://github.com/user-attachments/assets/4dc90564-ae15-44a3-99c2-c6b7dcf90a07)

Step 11: Use kubectl describe for Debugging
   kubectl describe pod <pod-name>
   
![Screenshot 2025-05-21 104151](https://github.com/user-attachments/assets/14e92079-9f35-45e1-a721-41e685a807d0)


Step 12: Use kubectl port-forward  
   kubectl port-forward service/nginx-service 8080:80
