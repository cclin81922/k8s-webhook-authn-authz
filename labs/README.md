# lab 1

Steps

1. Create a http server pod in `kube-system` namespace
2. Expose the http server pod 
3. Ping the http server pod from `kube-apiserver-docker-for-desktop` pod in `kube-system` namespace
4. Delete the http server pod
5. Delete the http server service

```
kubectl run httpd -n kube-system --image=httpd:2.4 --restart=Never --port=80 --expose=true

# output
#
# service "httpd" created
# pod "httpd" created

kubectl exec kube-apiserver-docker-for-desktop ping httpd.kube-system -n kube-system

# output
#
# ping: cannot resolve httpd.kube-system: Unknown host

kubectl delete po/httpd -n kube-system

# output
#
# pod "httpd" deleted

kubectl delete svc/httpd -n kube-system

# output
#
# svc "httpd" deleted
```

# lab 2

Steps

1. Create a https server pod in `kube-system` namespace
2. Expose the https server pod 
3. Curl the https server pod from `kube-apiserver-docker-for-desktop` pod in `kube-system` namespace
4. Delete the https server pod
5. Delete the https server service

# lab 3

Steps

1. Create a https server pod in `kube-system` namespace
2. Expose the https server pod 
3. Curl the https server pod from `kube-apiserver-docker-for-desktop` pod in `kube-system` namespace with mutual TLS authentication
4. Delete the https server pod
5. Delete the https server service
