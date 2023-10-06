# ansible-kubernetes
This Ansible playbook automates Kubernetes resource deployment, creating a "my-app" namespace and deploying Nginx. It requires kubeconfig.yaml for authentication and uses nginx.yaml for resource definitions.


This Ansible playbook is designed to automate the deployment of Kubernetes resources, including the creation of a Kubernetes namespace and the deployment of an Nginx application within that namespace. Here's a description of what the code does:

The playbook is named "deploy to k8s."

It is intended to be executed on the "localhost," meaning it will run on the machine where Ansible is installed.

The playbook consists of two main tasks:

Create Kubernetes Namespace:

Task Name: "create k8s namespace"
Action: This task uses Ansible's k8s module to create a Kubernetes namespace named "my-app" if it doesn't already exist (state: present).
Kubernetes API Version: api_version: v1
Kubernetes Kind: kind: namespace
Kubernetes Configuration: The kubeconfig parameter specifies the path to the Kubernetes configuration file (kubeconfig.yaml) used for authentication and cluster configuration. In this case, it points to an absolute file path.
Deploy Nginx Application:

Task Name: "deploy nginx app"
Action: This task uses Ansible's k8s module to deploy an Nginx application to the Kubernetes cluster.
src Parameter: Specifies the path to the Kubernetes resource definition file (nginx.yaml) for the Nginx application. It uses an absolute file path.
state Parameter: Sets the desired state for the resources. In this case, it's set to present, indicating that Ansible should ensure that the resources defined in nginx.yaml are present in the cluster.
kubeconfig Parameter: Similar to the previous task, this parameter specifies the path to the Kubernetes configuration file (kubeconfig.yaml) for authentication and cluster configuration.
namespace Parameter: Specifies the target namespace where the Nginx application should be deployed. In this case, it's set to "my-app," which corresponds to the namespace created in the first task.
Overall, this playbook automates the process of creating a Kubernetes namespace and deploying an Nginx application within that namespace. It assumes that the necessary Kubernetes configuration and resource definitions are available at the specified paths.


<img width="567" alt="Screenshot 2023-10-07 at 12 26 42 AM" src="https://github.com/Tushar240503/ansible-kubernetes/assets/98592305/d5187bd2-4df4-4e99-8207-1d0308076f2b">



