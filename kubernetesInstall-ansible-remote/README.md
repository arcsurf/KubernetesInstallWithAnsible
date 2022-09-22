**Prepare the server**
======================================================
***Python and Ansible Install:***

- ./01-installPythonAnsible.sh


**Update Server**
======================================================

- ansible-playbook 02-updateServer.yml -i inventory.txt --limit "HOSTNAME"


**Install Kubelet Kubeadm Kubectl**
======================================================
- ansible-playbook -i inventory.txt --limit "HOSTNAME" 03-InstallKubeletKubeadmKubectl.yml


**Disable Swap in Host "bareMetal or VM"**
===========================================================================
- ansible-playbook -i inventory.txt --limit "HOSTNAME" 04-disableSwap.yml


**Enable Kernel Modules**
======================================================

- ansible-playbook -i inventory.txt --limit "HOSTNAME" 05-enableKernelModules.yml


**Install CRI-O Container Runtime**
======================================================

- ansible-playbook -i inventory.txt --limit "HOSTNAME" 06-installContainerRuntime.yml


**Initialize Master Node**
======================================================

- ansible-playbook -i inventory.txt --limit "HOSTNAME" 07-initializeMasterNode.yml

**Install Calico Network Plugin**
======================================================

- ansible-playbook -i inventory.txt --limit "HOSTNAME" 08-installNetworkPluginOnMaster.yml
