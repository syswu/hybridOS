
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

### 1.2 disable scheduler and controller-manager

