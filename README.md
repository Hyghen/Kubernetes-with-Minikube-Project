# Kubernetes with Minikube Project

A minimal, hands-on example demonstrating how to deploy a simple application on Kubernetes using Minikube and `kubectl`.

---

##  Overview

This repository contains:

- `deployment.yaml` — Kubernetes Deployment manifest for your app

- `service.yaml` — Kubernetes Service manifest exposing the app

- This README — step-by-step instructions to deploy, access, scale, and clean up.

---

##  Prerequisites

- A VM or system with virtualization enabled

- Minikube must be installed

- kubectl must be installed

- Docker, if you’re building images locally

---

##  Step-by-Step explanation of what i have done 

### 1. Start Minikube
  
  -- minikube start

2. Verify Cluster Status

  -- kubectl cluster-info
  
  -- kubectl get nodes

3. Deploy Your Application

   -- kubectl apply -f deployment.yaml

   -- kubectl apply -f service.yaml

5. Check Pod and Service Status

   -- kubectl get pods

    <img width="986" height="153" alt="Screenshot 2025-08-11 102644" src="https://github.com/user-attachments/assets/6c029cc6-0f21-4fd8-84e5-0f466f03c630" />

   
  -- kubectl get svc

  <img width="1095" height="152" alt="Screenshot 2025-08-11 102723" src="https://github.com/user-attachments/assets/141d60f1-d417-4e9a-84ae-a2a15a18df01" />


6. Open the App in Your Browser

   -- minikube service myapp-service

   <img width="1133" height="437" alt="Screenshot 2025-08-11 102833" src="https://github.com/user-attachments/assets/a06fd900-fd0e-4a86-b904-24089cd82287" />


8. Scale the Deployment 

   -- kubectl scale deployment myapp-deployment --replicas=5

   <img width="1487" height="501" alt="Screenshot 2025-08-11 103015" src="https://github.com/user-attachments/assets/df758013-6a89-447f-a19d-d57032d9dc95" />

   
  -- kubectl get pods

  <img width="1011" height="237" alt="Screenshot 2025-08-11 102940" src="https://github.com/user-attachments/assets/35479027-0ec8-4463-b2da-a934776dde85" />


10. Inspect Logs and Pod Details
  
  -- kubectl get pods
    
  -- kubectl describe pod <pod-name>
  
  -- kubectl logs <pod-name>

  <img width="1698" height="312" alt="Screenshot 2025-08-11 103204" src="https://github.com/user-attachments/assets/aa2bed97-7b53-404a-a1b5-a87e7a4e8316" />


Cleanup
Once you're done testing:

  -- kubectl delete -f service.yaml
  
  -- kubectl delete -f deployment.yaml
  
  -- minikube stop
 
  -- minikube delete  # if you want to remove the cluster entirely
