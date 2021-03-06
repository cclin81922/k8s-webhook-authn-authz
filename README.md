# k8s-webhook-authn-authz

Prerequisites

* Your own TLS certificate authority: `ca.crt`
* Self-signed server certificate issued by your own TLS certificate authority: `webhook-server.crt`
* Self-signed client certificate issued by your own TLS certificate authority: `webhook-client.crt`

Usage

```
cd webhook-machine
vagrant up

# k8s-apiserver - - ping - - > webhook-machine
# kubectl exec kube-apiserver-docker-for-desktop ping 192.168.33.101 -n kube-system
```

Configure `k8s-apiserver` then restart it

```
screen ~/Library/Containers/com.docker.docker/Data/com.docker.driver.amd64-linux/tty

# download files
#
# * ca.crt
# * webhook-client.crt
# * webhook-client.key

# mod /etc/kubernetes/manifests/kube-apiserver.yaml
```

Test via kubectl

```
?
```

# Reference

* Sample k8s authn / authz webhook [[blog]](https://medium.com/google-cloud/kubernetes-webhook-authentication-authorization-with-minikube-67b2b385ffd1) [[src]](https://github.com/salrashid123/k8s_webhook_helloworld)
* Example authn / authz webhook - yahoo/k8s-athenz-webhook [[src]](https://github.com/yahoo/k8s-athenz-webhook)
* [Mutual TLS authentication between k8s-apiserver and authn webhook](https://kubernetes.io/docs/admin/authentication/#webhook-token-authentication)
* [Mutual TLS authentication between k8s-apiserver and authz webhook](https://kubernetes.io/docs/admin/authorization/webhook/#configuration-file-format)
