# Before writing pipeline Do the connection between Jenkins and k8s
---**Do the below settings on Jenkins Machin**
# Set the latest stable version of kubectl
KUBECTL_VERSION=$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)

# Download kubectl binary
curl -LO "https://storage.googleapis.com/kubernetes-release/release/${KUBECTL_VERSION}/bin/linux/amd64/kubectl"

# Make it executable
chmod +x kubectl

# Move to /usr/local/bin
sudo mv kubectl /usr/local/bin/


**Create a directory in jenkins machin and copy the config data from K8s and past it here**
mkdir -p ~/.kube
vi ~/.kube/config
chmod 600 ~/.kube/config    -- give permission

**Then test the connection between jenkins and k8s on jenkins machin**
kubectl get nodes
