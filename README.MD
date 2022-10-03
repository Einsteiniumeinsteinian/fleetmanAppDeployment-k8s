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

2. #### setup application services

webapp:

```k8
kubectl apply -f webapp/webappServices
```

queue:

```k8
kubectl apply -f queue/queueServices
```

gateway:

```k8
kubectl apply -f gateway/gatewayServices
```

tracker:

```k8
kubectl apply -f tracker/tracker
```

3. #### setup applications

queue:

```k8
kubectl apply -f queue/queue
```

gateway:

```k8
kubectl apply -f gateway/gateway
```

tracker:

```k8
kubectl apply -f tracker/tracker
```

```k8
kubectl apply -f simulator/simulator
```

```k8
kubectl apply -f webapp/webapp
```
