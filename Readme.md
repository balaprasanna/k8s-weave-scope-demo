
## install weave-scope visualizer
```
$ helm install stable/weave-scope --name weave
```

## Result
```
NAME:   weave
LAST DEPLOYED: Thu Nov 28 22:46:21 2019
NAMESPACE: default
STATUS: DEPLOYED

RESOURCES:
==> v1/ConfigMap
NAME                     AGE
weave-scope-weave-tests  1s

==> v1/DaemonSet
NAME                     AGE
weave-scope-agent-weave  0s

==> v1/Deployment
NAME                             AGE
weave-scope-cluster-agent-weave  0s

==> v1/Pod(related)
NAME                                              AGE
weave-scope-agent-weave-8mlsn                     0s
weave-scope-agent-weave-gcnz9                     0s
weave-scope-agent-weave-w59vl                     0s
weave-scope-cluster-agent-weave-7b8c84d95f-mwmr7  0s
weave-scope-frontend-weave-5644984b6b-ddq7h       0s

==> v1/Service
NAME               AGE
weave-weave-scope  1s

==> v1/ServiceAccount
NAME                             AGE
weave-scope-cluster-agent-weave  1s

==> v1beta1/ClusterRole
NAME                             AGE
weave-scope-cluster-agent-weave  1s

==> v1beta1/ClusterRoleBinding
NAME               AGE
weave-weave-scope  1s

==> v1beta1/Deployment
NAME                        AGE
weave-scope-frontend-weave  0s


NOTES:
You should now be able to access the Scope frontend in your web browser, by
using kubectl port-forward:

kubectl -n default port-forward $(kubectl -n default get endpoints \
weave-weave-scope -o jsonpath='{.subsets[0].addresses[0].targetRef.name}') 8080:4040

then browsing to http://localhost:8080/.
For more details on using Weave Scope, see the Weave Scope documentation:

https://www.weave.works/docs/scope/latest/introducing/
```


## Access the UI

```
 kubectl -n default port-forward $(kubectl -n default get endpoints weave-weave-scope -o jsonpath='{.subsets[0].addresses[0].targetRef.name}') 8080:4040
```
