# Install Kubernetes nodes with ansible
This script assume you already configure access from your ansible host to your nodes: <br>
To run this ansible play book, you need all 3 files: <br>
**instkuber-node.yml** is based on instruction of installation kubernetes on the offical [site](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/) <br>
**kube-nodes** is list of nodes that you want install kubeadm, kubectl, and kubelet to: <br>
**join-command** is the script to join these newly kubernetes nodes to an existing cluster (master)<br>
You must update join-command content with the out put of "kubeadm token create --print-join-command" of your cluster master.<br>
<br>
ansible-playbook -i kube-nodes instkuber-nodes.yml --ask-become-pass
