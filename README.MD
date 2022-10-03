# Fleetman vehicle Documentation

Tracks company's vehicles using fleetman app.

---

## Application setup

- frontend: (fleetman-webapp, loadbalancer service)
- gateway: (fleetman-gateway, ClusterIp service)
- tracker: (fleetman-position-tracker, ClusterIp service)
- queue: (fleetman-queue, ClusterIp service)
- simulator: (fleetman-simulator)

---

### Steps

1. #### if the namespace does not exist create the namespace

verify namesapace using:

```k8
kubectl get ns
```

create namespace using:

```k8
kubectl apply -f namespace.yml
```

2. #### setup application and corresponding services

queue:

```k8
kubectl apply -f queue
```

gateway:

```k8
kubectl apply -f gateway
```

tracker:

```k8
kubectl apply -f tracker
```

webapp:

```k8
kubectl apply -f webapp
```
