# Installing the Client Tools

First identify a system from where you will perform administrative tasks, such as creating certificates, kubeconfig files and distributing them to the different VMs.

If you are on a Linux laptop, then your laptop could be this system. In my case I chose the master-1 node to perform administrative tasks. Whichever system you chose make sure that system is able to access all the provisioned VMs through SSH to copy files over.

## Access all VMs

Generate Key Pair on master-1 node
`$ssh-keygen`

Leave all settings to default.

View the generated public key ID at:

```
$cat .ssh/id_rsa.pub
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQD......8+08b vagrant@master-1
```

Move public key of master to all other VMs

```
$cat >> ~/.ssh/authorized_keys <<EOF
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQD......8+08b vagrant@master-1
EOF
```


## Install kubectl

The [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl). command line utility is used to interact with the Kubernetes API Server. Download and install `kubectl` from the official release binaries:

Reference: [https://kubernetes.io/docs/tasks/tools/install-kubectl/](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

### Linux

if you're using linux and on ubuntu you can use the kubectl playbook that uses the kubectl role. 

### Verification

Playbook will print the version installed 

> output

```
ok: [node1] => {
    "kube_version['stdout']": "Client Version: version.Info{Major:\"1\", Minor:\"25\", GitVersion:\"v1.25.0\", GitCommit:\"a866cbe2e5bbaa01cfd5e969aa3e033f3282a8a2\", GitTreeState:\"clean\", BuildDate:\"2022-08-23T17:44:59Z\", GoVersion:\"go1.19\", Compiler:\"gc\", Platform:\"linux/amd64\"}\nKustomize Version: v4.5.7"
}
```

Next: [Certificate Authority](04-certificate-authority.md)
