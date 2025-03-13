# Amazon-EKS-Elastic-Kubernetes-Service-cluster

How to Use:
Save the variables.tf and main.tf files in the same directory.

# Initialize Terraform:
terraform init
# Review the plan:
terraform plan
# Apply the configuration:
terraform apply

# After creating the EKS cluster, you need to configure your local environment to interact with the cluster using kubectl. Here are the steps to access and manage your EKS cluster:

Step 1: Install Required Tools
Install kubectl
Install awscli
Install eksctl (Optional)

Step 2: Update kubeconfig
# To access your EKS cluster, you need to update your local kubeconfig file with the cluster's credentials.

# aws eks --region <region> update-kubeconfig --name <cluster-name>

(This command updates your ~/.kube/config file with the cluster's API server endpoint and authentication credentials.)

Step 3: Verify Access

# kubectl get nodes
(This should list the worker nodes in your EKS cluster. If the command succeeds, you have successfully configured access to your EKS cluster.)


Step 4: Deploy Applications
Now that you have access to the cluster, you can deploy applications using kubectl. For example:

Step 4: Deploy Applications

Now that you have access to the cluster, you can deploy applications using kubectl. For example:
  1. kubectl create deployment nginx --image=nginx
  2. kubectl expose deployment nginx --port=80 --type=LoadBalancer
  3. kubectl get svc
    (Look for the EXTERNAL-IP of the nginx service to access it in your browser.)

Step 5: Manage the Cluster
You can use kubectl to manage your cluster:
# View pods:
  kubectl get pods

# View services:
  kubectl get svc

# View deployments:
  kubectl get deployments

# View cluster info:
  kubectl cluster-info

# Troubleshooting
Permission Issues:

Ensure your AWS IAM user or role has the necessary permissions to access the EKS cluster.

Attach the **AmazonEKSClusterPolicy** and **AmazonEKSWorkerNodePolicy** policies to your IAM user/role.

kubectl Command Fails:

Verify that your kubeconfig file is correctly updated.

Ensure your AWS credentials are configured correctly using aws configure.

Nodes Not Showing Up:

Check the node group status in the AWS EKS console.

Ensure the worker nodes are in a healthy state.


![image](https://github.com/user-attachments/assets/5b8a38c5-bd49-4ce2-a3f0-bc4d8c2f04ae)

![image](https://github.com/user-attachments/assets/00d681fa-2c26-4ee3-b994-3cc66bc66882)

![image](https://github.com/user-attachments/assets/153f7d67-ea53-43b4-8425-7ba73ed3cbbc)


