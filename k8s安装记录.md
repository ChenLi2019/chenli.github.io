#升级
- k8s升级不支持跨多版本升级，主版本号间隔不能超过1，例如你的主版本号是15，最新版本号是17,你要先升级到16才能再升级到17.
- 下载历史版本，centos下，ubuntu类似
  - yum install ./ kubeadm-1.16.0-0 kubectl-1.16.0-0 kubelet-1.16.0-0
- 提前pull集群需要下载的镜像 kubeadm config images pull
