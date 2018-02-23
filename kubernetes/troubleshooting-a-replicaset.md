# Troubleshooting a ReplicaSet

Sometimes a deployment will fail with no apparent reason:

```
$ kubectl describe deployment example
[...]
  Type    Reason             Age   From                   Message
  ----    ------             ----  ----                   -------
  Normal  ScalingReplicaSet  1m    deployment-controller  Scaled up replica set gaudy-sasquatch-example-9d5559f5d to 1
```

One solution is to check the ReplicaSet status. A hint can be seen in the
Deployment description:

```
$ kubectl describe deployment example
[...]
Replicas:               1 desired | 0 updated | 0 total | 0 available | 1 unavailable
[...]
```

The ReplicaSet description will show the problem:

```
$ kubectl describe replicaset example
[...]
  Type     Reason        Age               From                   Message
  ----     ------        ----              ----                   -------
  Warning  FailedCreate  2s (x17 over 5m)  replicaset-controller  Error creating: pods "gaudy-sasquatch-example-9d5559f5d-" is forbidden: error looking up service account default/example: serviceaccount "example" not found
```
