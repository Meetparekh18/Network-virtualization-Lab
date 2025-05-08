sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils
   sudo apt install openstack
   kubectl apply -f nfv-deployment.yaml

   
**src/nfv-deployment.yaml**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nfv-deployment
spec:
  replicas: 2
  selector:
    matchLabels:
      app: nfv
  template:
    metadata:
      labels:
        app: nfv
    spec:
      containers:
      - name: nfv-container
        image: alpine
        command: ["sleep", "infinity"]

