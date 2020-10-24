# Install compilation and source code git tool
sudo su - 

apt install -y gcc make socat git

# Install etcd
curl -L https://github.com/coreos/etcd/releases/download/v3.4.13/etcd-v3.4.13-linux-amd64.tar.gz -o etcd-v3.4.13-linux-amd64.tar.gz && tar xzvf etcd-v3.4.13-linux-amd64.tar.gz && /bin/cp -f etcd-v3.4.13-linux-amd64/{etcd,etcdctl} /usr/bin &amp;&amp; rm -rf etcd-v3.4.13-linux-amd64*

# Install golang
curl -sL https://storage.googleapis.com/golang/go1.15.linux-amd64.tar.gz | tar -C /usr/local -zxf -

# Add it to your PATH
export GOPATH=/gopath

export PATH=$PATH:$GOPATH/bin:/usr/local/bin:/usr/local/go/bin/

# Get kubernetes source code
git clone --depth 1 https://github.com/kubernetes/kubernetes

# Add kubernetes source code to GOPATH
git clone https://github.com/kubernetes/kubernetes $GOPATH/src/k8s.io/kubernetes

cd $GOPATH/src/k8s.io/kubernetes

# Compile and run kubernetes (will take some time)
export KUBERNETES_PROVIDER=local

hack/local-up-cluster.sh

# Connect to local k8s in a new shell
export GOPATH=/gopath

export PATH=$PATH:$GOPATH/bin:/usr/local/bin:/usr/local/go/bin/

cd $GOPATH/src/k8s.io/kubernetes

export KUBERNETES_PROVIDER=local

cluster/kubectl.sh config set-cluster local --server=http://127.0.0.1:8080 --insecure-skip-tls-verify=true

cluster/kubectl.sh config set-context local --cluster=local

cluster/kubectl.sh config use-context local


# Test local k8s
cluster/kubectl.sh cluster-info

Kubernetes master is running at http://127.0.0.1:8080 # =&gt; Great!


## Possible Issues

Minimum supported version of golang and etcd might have changed since this is documented. Use the minimum supported versions of these softwares accordingly


## References

https://dzone.com/articles/easy-step-by-step-local-kubernetes-source-code-cha



