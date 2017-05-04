# Creating a cluster

```
mkdir -p ~/workspace
cd ~/workspace
git clone https://github.com/tomdee/kubeadm-vagrant
vagrant up
vagrant ssh-config > ~/.ssh/vagrant-ssh-config
pushd ~/.ssh && cat vagrant-ssh-config >> config && popd
ssh n1 sudo kubeadm init --apiserver-advertise-address=192.168.77.10 --pod-network-cidr 10.244.0.0/16

# Then do the join from n2 and n3 by following the output of the above command

# Set up kubectl
ssh n1 ‘sudo cp /etc/kubernetes/admin.conf $HOME/’
scp n1:admin.conf .
export KUBECONFIG=$HOME/workspace/kubeadm-vagrant/admin.conf
```
