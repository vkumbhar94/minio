# MinIO on Docker Desktop Kubernetes

Deploy MinIO object storage on Docker Desktop Kubernetes with persistent storage.

## Prerequisites

- Docker Desktop with Kubernetes enabled
- `kubectl` command-line tool

## Quick Start

Apply the manifest to your Docker Desktop K8s cluster:

```bash
kubectl apply -f minio-manifest.yaml
```

## Verify Deployment

Check the status:

```bash
kubectl get pods
kubectl get svc
```

Wait for the `minio` pod to be in `Running` state and the `s3` service to have an external IP.

## Access MinIO

Once deployed, access MinIO through:

- **API Endpoint**: http://localhost:9000
- **Console UI**: http://localhost:9001

### Default Credentials

- **Username**: `minio`
- **Password**: `minio_key`

## Cleanup

To remove MinIO from your cluster:

```bash
kubectl delete -f minio-manifest.yaml
```

This will remove the StatefulSet, Service, and PersistentVolumeClaim.

## Storage

Data is persisted in a Kubernetes PersistentVolume managed by Docker Desktop. The PVC size is configured to 2Gi.
