**Managed by kubelet daemon:**
Static Pods are managed directly by the kubelet daemon on a specific node,
without the API server observing them.

Unlike Pods that are managed by the control plane (for example, a Deployment); 
instead, the kubelet watches each static Pod (and restarts it if it fails).

**Bound to one kubelet:**
Static Pods are always bound to one Kubelet on a specific node.

**Cannot be controlled on API server:**
The kubelet automatically tries to create a mirror Pod on the Kubernetes API server for each static Pod. This means that the Pods running on a node are visible on the API server, but cannot be controlled from there.

**Cannot refer to other API objects:**
The spec of a static Pod cannot refer to other API objects (e.g., ServiceAccount, ConfigMap, Secret, etc).

Reference:
https://kubernetes.io/docs/tasks/configure-pod-container/static-pod/

