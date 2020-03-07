# kubernetes-training

Create a Kubernetes cluster with Vagrant, Ansible and VirtualBox.

## Prerequisites

Last tested with:

- Vagrant 2.2.6
- VirtualBox 6.0
- [kubectl 1.16.2](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

## Setting up a Kubernetes cluster

Choose one of the OS directories.

The `Vagrantfile` can be used to start VMs for a Kubernetes cluster:

- One master, `k8s-master`
- Two workers, `k8s-node-0` and `k8s-node-1`

### Create and provision machines

```sh
vagrant up
```

### Configure the Kubernetes cluster

```sh
./cluster-up.sh
```

### Configure local kubectl for Kubernetes cluster

```sh
cp -i config ~/.kube/
```

### Verify

```sh
$ kubectl get nodes
NAME           STATUS     ROLES     AGE       VERSION
k8s-master     Ready      master    48s       v1.9.1
k8s-node-0     Ready      <none>    29s       v1.9.1
k8s-node-1     Ready      <none>    23s       v1.9.1
```

### Destroy machines

```sh
vagrant destroy -f
```
