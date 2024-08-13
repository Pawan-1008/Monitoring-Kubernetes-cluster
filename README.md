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

➔ Kubectl create ns monitoring
➔ Kubectl get ns


STEP-5





