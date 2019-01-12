# kubernetes-training

Create a Kubernetes cluster with Vagrant and VirtualBox.

## Prerequisites

Last tested with:

- Vagrant 2.2.3
- VirtualBox 6.0
- [kubectl 1.13.1](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

## Setting up a Kubernetes cluster

Choose one of the OS directories.

The `Vagrantfile` can be used to start VMs for a Kubernetes cluster:

- One master, `k8s-master`
- Two workers, `k8s-worker-0` and `k8s-worker-1`

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
k8s-worker-0   Ready      <none>    29s       v1.9.1
k8s-worker-1   Ready      <none>    23s       v1.9.1
```

### Destroy machines

```sh
vagrant destroy -f
```
