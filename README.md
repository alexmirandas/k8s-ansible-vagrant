# kubernetes-ansible-and-vagrant #

Kubernetes Setup Using Ansible and Vagrant

**Objective**
This blog post describes the steps required to setup a multi node Kubernetes cluster for development purposes.
This setup provides a production-like cluster that can be setup on your local machine.

**Why use Vagrant and Ansible?**
Vagrant is a tool that will allow us to create a virtual environment easily and it eliminates pitfalls that cause the works-on-my-machine phenomenon. It can be used with multiple providers such as Oracle VirtualBox, VMware, Docker, and so on. It allows us to create a disposable environment by making use of configuration files.

Ansible is an infrastructure automation engine that automates software configuration management. It is agentless and allows us to use SSH keys for connecting to remote machines. Ansible playbooks are written in yaml and offer inventory management in simple text files.

# Prerequisites
``` 
  - Vagrant should be installed on your machine-
  - Oracle VirtualBox
  - Ansible should be installed in your machine
``` 

# Setup overview
We will be setting up a Kubernetes cluster that will consist of one master and two worker nodes. All the nodes will run Ubuntu Xenial 64-bit OS and Ansible playbooks will be used for provisioning.

```
  $ cd /path/to/Vagrantfile
  $ vagrant up
```

Upon completion of all the above steps, the Kubernetes cluster should be up and running. We can login to the master or worker nodes using Vagrant as follows

```
  $ ## Accessing master
  $ vagrant ssh k8s-master
  
  vagrant@k8s-master:~$ kubectl get nodes
  NAME         STATUS   ROLES    AGE     VERSION
  k8s-master   Ready    master   18m     v1.13.3
  node-1       Ready    <none>   12m     v1.13.3
  node-2       Ready    <none>   6m22s   v1.13.3

  $ ## Accessing nodes
  $ vagrant ssh node-1
  $ vagrant ssh node-2
```

```
 ___    ___
( _<    >_ )
//        \\
\\___..___//
 `-(    )-'
   _|__|_
  /_|__|_\
  /_|__|_\
  /_\__/_\
   \ || /  _)
     ||   ( )
     \\___//
      `---'
By: Alex Miranda

```


