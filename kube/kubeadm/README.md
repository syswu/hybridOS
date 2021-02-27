
## 1. kubeadm 

### 1.1 minimize resources
cmd/kubeadm/app/constants/constants.go

```
                // ControlPlaneNumCPU is the number of CPUs required on control-plane
	ControlPlaneNumCPU = 2

	// ControlPlaneMem is the number of megabytes of memory required on the control-plane
	// Below that amount of RAM running a stable control plane would be difficult.
	ControlPlaneMem = 1700
```

### 1.2 ignore scheduler and controller-manager

cmd/kube-apiserver/app/phases/controlplane/manifests.go

cat cmd/kube-apiserver/app/phases/controlplane/manifests.go | grep -A 1 "func CreateInitStaticPodManifestFiles"

```
-  return CreateStaticPodFiles(manifestDir, patchesDir, &cfg.ClusterConfiguration, &cfg.LocalAPIEndpoint, kubeadmconstants.KubeAPIServer, kubeadmconstants.KubeControllerManager, kubeadmconstants.KubeScheduler)
+ return CreateStaticPodFiles(manifestDir, patchesDir, &cfg.ClusterConfiguration, &cfg.LocalAPIEndpoint, kubeadmconstants.KubeAPIServer)
```
