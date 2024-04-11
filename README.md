### Sources:
#### Youtube: https://www.youtube.com/watch?v=tivL8sNbPik
- After launching all yaml files, got this, **need to look into the ebs.csi.aws.com provisioner**
```
$ k describe pvc ebs-claim        
Name:          ebs-claim
Namespace:     default
StorageClass:  stateful-app-sg
Status:        Pending
Volume:        
Labels:        <none>
Annotations:   volume.beta.kubernetes.io/storage-provisioner: ebs.csi.aws.com
               volume.kubernetes.io/selected-node: lima-rancher-desktop
               volume.kubernetes.io/storage-provisioner: ebs.csi.aws.com
Finalizers:    [kubernetes.io/pvc-protection]
Capacity:      
Access Modes:  
VolumeMode:    Filesystem
Used By:       sg-app
Events:
  Type    Reason                Age                From                         Message
  ----    ------                ----               ----                         -------
  Normal  WaitForFirstConsumer  15s (x6 over 79s)  persistentvolume-controller  waiting for first consumer to be created before binding
  Normal  ExternalProvisioning  0s (x3 over 4s)    persistentvolume-controller  Waiting for a volume to be created either by the external provisioner 'ebs.csi.aws.com' or manually by the system administrator. If volume creation is delayed, please verify that the provisioner is running and correctly registered.
```
#### Follow https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/ with my own change
- mountPath and echo output path need to be the same
