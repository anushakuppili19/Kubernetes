# To download the latest stable version of kubectl, run:
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl

# After the download is complete, make the binary executable and move it to a directory included in your PATH:
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl

# Verify the installation by checking the client version. Note that until a cluster is running, you might encounter a message about the connection being refused:
kubectl version

# Example output:
Client Version: version.Info{Major:"1", Minor:"18", GitVersion:"v1.18.5", GitCommit:"6503f8d8f769ace2f338794c914a96fc335df0f", GitTreeState:"clean", BuildDate:"2020-06-26T03:47:41Z", GoVersion:"go1.13.9", Compiler:"gc", Platform:"linux/amd64"}

# The connection to the server localhost:8080 was refused - did you specify the right host or port?

# Other installation methods are available in the Kubernetes documentation. For example, on Ubuntu you might use:
sudo apt-get update && sudo apt-get install -y apt-transport-https gnupg2
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubectl
