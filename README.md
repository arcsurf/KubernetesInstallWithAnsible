**Prepare the server**
======================================================
***Python and Ansible Install:***

- ./01-installPythonAnsible.sh


**Update Server**
======================================================
- [ ] ansible-playbook --ask-become-pass 02-updateServer.yml


**Install Kubelet Kubeadm Kubectl**
======================================================
- [ ] ansible-playbook --ask-become-pass 03-InstallKubeletKubeadmKubectl.yml


**Disable Swap in Host "bareMetal or VM"**
===========================================================================
- [ ] ansible-playbook --ask-become-pass 04-disableSwap.yml


**Enable Kernel Modules**
======================================================

- [ ] ansible-playbook --ask-become-pass 05-enableKernelModules.yml


**Install CRI-O Container Runtime**
======================================================

- [ ] ansible-playbook --ask-become-pass 06-installContainerRuntime.yml


**Initialize Master Node**
======================================================

- [ ] ansible-playbook -e "serverIp=\<nodeIp\> serverFqdn=\<nodeHOstName\>" --ask-become-pass ./07-initializeMasterNode.yml
  > I.E: ansible-playbook -e "serverIp=192.168.1.101 serverFqdn=k8s-master-01" --ask-become-pass ./07-initializeMasterNode.yml

**Install Calico Network Plugin**
======================================================

- [ ] ansible-playbook --ask-become-pass ./08-installNetworkPluginOnMaster.yml
