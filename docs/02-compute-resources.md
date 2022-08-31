# Provisioning Compute Resources

Note: You must have XCP-NG and Ansible configured at this point

Download this github repository and cd into the ansible folder

`git clone https://github.com/smiggiddy/kubernetes-the-hard-way.git`

CD into ansible directory and grab the playbooks you need

`cd kubernetes-the-hard-way\ansible`


You'll need to provision 5-6 VMs. You can use whatever OS you like. I am using Ubuntu 20.04.3 Cloud Init Template Image. I provisioned each machine with 2 VCPUs and 4 GB of Ram each. For the Loadbalancer I will be provisioning an Alpine VM. 

assign a naming convention you'd like to use. 

- I am using `smig-lab-k8s-cpX` for the control plane nodes.  
`smig-lab-k8s-wnX` for the worker nodes. `smig-lab-lbX` for the loadbalancer. 

- I will be using DHCP to assign IP addresses to each node. I also have DNS configured. 



- Install's Docker on Worker nodes
- Runs the below command on all nodes to allow for network forwarding in IP Tables.
  This is required for kubernetes networking to function correctly.
    > sysctl net.bridge.bridge-nf-call-iptables=1


## SSH to the nodes

There are two ways to SSH into the nodes:

### SSH Using SSH Client Tools

Use your favourite SSH Terminal tool (putty).

you'll need to use the ssh keys to get into the vm's if you used the templates. 


**Username:** `ubuntu`


## Verify Environment

- Ensure all VMs are up
- Ensure VMs are assigned the IP addresses via dhcp server
- Ensure you can SSH into these VMs using the IP and private keys (run svc-ansible provision playbook)
- Ensure the VMs can ping each other
- Ensure the worker nodes have Docker installed on them. (run docker playbook)
    - Version: 19.03.8
  > command `sudo docker version`





