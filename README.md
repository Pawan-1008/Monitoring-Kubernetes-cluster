# Monitoring-Kuberrnetes-cluster

Scenario:

Your team requires monitoring capabilities for your Kubernetes cluster. This task focuses on deploying Prometheus and Grafana to collect and visualize application and infrastructure metrics.


Introduction:

Kubernetes: Kubernetes is a portable, extensible, open source platform for managing containerized workloads and services, that facilitates both declarative configuration
and automation.

Prometheus: Prometheus collects and stores its metrics as time series data, i.e. metrics information is stored with the timestamp at which it was recorded, alongside
optional key-value pairs called labels.

Grafana: Grafana open source is open source visualization and analytics software. It allows you to query, visualize, alert on, and explore your metrics, logs, and traces no
matter where they are stored.




Architechture:

![image](https://github.com/user-attachments/assets/3434b420-8319-4154-a2cc-603f332143c7)




Installation: 

STEP-1

Setting up cluster in the following manner by the given reference below.

https://github.com/Pawan-1008/k8s_installation/tree/main


STEP-2

![image](https://github.com/user-attachments/assets/1e2adfb5-6175-4cd9-89ab-0aa4488f7ef1)

After the your cluster is in ready state then follow the next steps.............


STEP-3


![image](https://github.com/user-attachments/assets/88fef7d3-80b1-4cf0-bd17-67bd288713e6)

We can see that the pods in kube-system namespace is in a ‘Running’ state.


STEP-4

![image](https://github.com/user-attachments/assets/6b8710da-afa5-4155-8cfb-571e2a30216b)

Creating a namespace named ‘monitoring’

➔ Kubectl create ns monitoring    ➔ Kubectl get ns



--------------------* Deploying Prometheus *--------------------

STEP-5

![image](https://github.com/user-attachments/assets/346f8b05-9fee-43f4-8faf-ddc2a89d114a)


➔ git clone https://github.com/bibinwilson/kubernetes-prometheus

➔ cd Kubernetes-prometheus

➔ kubectl apply -f .

#get the list of pods in namespace ‘monitoring’.
➔ kubectl get pods -n monitoring


#get the list of services in namespace ‘monitoring’
➔ kubectl get svc -n monitoring



--------------------* Accessing Prometheus and monitoring the k8s processes *--------------------

STEP-6

![image](https://github.com/user-attachments/assets/8211c160-ba1b-4e7e-b516-fe7937c03263)

![image](https://github.com/user-attachments/assets/d9fab653-357f-4f46-94ad-16c1283b3a56)


➔ ufw allow 30000/TCP

➔ ufw reload

#Access the NodePort with our Ubuntu 20.04 VM IP as follows.
➔ http://<ubuntu_IP>:<NodePort>



--------------------* Deploying Grafana *--------------------

➔ git clone https://github.com/Pawan-1008/grafana/tree/main

➔ cd grafana

➔ kubectl apply -f .

➔ ufw allow 32000/tcp

➔ ufw reload

➔ http://<ubuntu_IP>:<NodePort_Of_Grafana>

➔ Login into the Grafana with

Username: admin, Password: admin
#You get the screen to reset the password, set password
according to your choice

![image](https://github.com/user-attachments/assets/058618f9-17fa-4536-bf7f-72f05794b36d)



![image](https://github.com/user-attachments/assets/03e3bd98-f61d-4954-82d6-4288ed570584)

importing dashboard -> we can use the 10000 port to monitor the k8s cluster


![image](https://github.com/user-attachments/assets/bd6c993c-e8e2-4664-8823-e9a5009bce7c)

 monitoring at cluster level


