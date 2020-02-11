# kubernetes-on-centos-from-zero

## Use 
 * CentOS-7-x86_64-Minimal-1908.iso

## To config interfaces
```command

$ nmtui 
$ ifconfig


```
<img src="https://github.com/danilodesousacubas/kubernetes-on-centos-from-zero/blob/master/interfaces-01.png?sanitize=true&raw=true" />


## Enter the following command to retrieve the Kubernetes repositories
```command

$ cat <<EOF > /etc/yum.repos.d/kubernetes.repo
[kubernetes]
name=Kubernetes
baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-x86_64
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://packages.cloud.google.com/yum/doc/yum-key.gpg https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
EOF

```

## Yum install
```command
    $ sudo yum install -y kubelet kubeadm kubectl
```
<img src="https://github.com/danilodesousacubas/kubernetes-on-centos-from-zero/blob/master/installs-packages.png?sanitize=true&raw=true" />

## Use sys adm, to enable and to start
```
systemctl enable kubelet
systemctl start kubelet
```