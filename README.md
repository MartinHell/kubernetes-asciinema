# kubernetes-asciinema
Deploy asciinema server on Kubernetes

## Deploy 

first create the namespace

```
kubectl create -f asciinema-ns.yaml
```

adjust configmaps and create them

```
kubectl -n asciinema create -f asciinema-cm.yaml
kubectl -n asciinema create cm asciinema-nginx --from-file=default.conf
```

create backend/app/frontend services

```
kubectl -n asciinema apply -f asciinema-backend.yaml
kubectl -n asciinema apply -f asciinema-app.yaml
kubectl -n asciinema apply -f asciinema-frontend.yaml
```
