# Kubernetes

Installing MicroK8's in ubuntu:
--------------------------------

Official Installation link : [Official Installation link](https://microk8s.io/docs/getting-started) 
Git-hub Installation link : [Git-hub Installation link](https://github.com/canonical/microk8s) 

Install MicroK8s with:
        
        sudo snap install microk8s --classic --channel=1.30

        ideelitserver2@ideelitserver2-PowerEdge-T40:~$ sudo snap install microk8s --classic
        microk8s (1.29/stable) v1.29.4 from Canonical✓ installed

Check the status:

        sudo microk8s status --wait-ready

        ideelitserver2@ideelitserver2-PowerEdge-T40:~$ sudo microk8s status --wait-ready
        microk8s is running
        high-availability: no
        datastore master nodes: 127.0.0.1:19001
        datastore standby nodes: none
        addons:
        enabled:
            dns                  # (core) CoreDNS
            ha-cluster           # (core) Configure high availability on the current node
            helm                 # (core) Helm - the package manager for Kubernetes
            helm3                # (core) Helm 3 - the package manager for Kubernetes
        disabled:
            cert-manager         # (core) Cloud native certificate management
            cis-hardening        # (core) Apply CIS K8s hardening
            community            # (core) The community addons repository
            dashboard            # (core) The Kubernetes dashboard
            gpu                  # (core) Alias to nvidia add-on
            host-access          # (core) Allow Pods connecting to Host services smoothly
            hostpath-storage     # (core) Storage class; allocates storage from host directory
            ingress              # (core) Ingress controller for external access
            kube-ovn             # (core) An advanced network fabric for Kubernetes
            mayastor             # (core) OpenEBS MayaStor
            metallb              # (core) Loadbalancer for your Kubernetes cluster
            metrics-server       # (core) K8s Metrics Server for API access to service metrics
            minio                # (core) MinIO object storage
            nvidia               # (core) NVIDIA hardware (GPU and network) support
            observability        # (core) A lightweight observability stack for logs, traces and metrics
            prometheus           # (core) Prometheus operator for monitoring and logging
            rbac                 # (core) Role-Based Access Control for authorisation
            registry             # (core) Private image registry exposed on localhost:32000
            rook-ceph            # (core) Distributed Ceph storage using Rook
            storage              # (core) Alias to hostpath-storage add-on, deprecated

Add user to group:

        sudo usermod -a -G microk8s $USER
        mkdir -p ~/.kube
        chmod 0700 ~/.kube

Alaising the microk8's command:

        echo "alias kubectl='microk8s kubectl'" > ~/.bash_aliases

To enable/disable add-ons:

        sudo microk8s enable <add-ons>
        sudo microk8s disable <add-ons>

        ideelitserver2@ideelitserver2-PowerEdge-T40:~$ sudo microk8s enable dns
        Infer repository core for addon dns
        Addon core/dns is already enabled

        ideelitserver2@ideelitserver2-PowerEdge-T40:~$ sudo microk8s enable hostpath-storage
        Infer repository core for addon hostpath-storage
        Enabling default storage class.
        WARNING: Hostpath storage is not suitable for production environments.
                A hostpath volume can grow beyond the size limit set in the volume claim manifest.

        deployment.apps/hostpath-provisioner created
        storageclass.storage.k8s.io/microk8s-hostpath created
        serviceaccount/microk8s-hostpath created
        clusterrole.rbac.authorization.k8s.io/microk8s-hostpath created
        clusterrolebinding.rbac.authorization.k8s.io/microk8s-hostpath created
        Storage will be available soon.

        ideelitserver2@ideelitserver2-PowerEdge-T40:~$ sudo microk8s disable cert-manager
        Infer repository core for addon cert-manager
        Deleting cert-manager
        namespace "cert-manager" deleted
        customresourcedefinition.apiextensions.k8s.io "certificaterequests.cert-manager.io" deleted
        customresourcedefinition.apiextensions.k8s.io "certificates.cert-manager.io" deleted
        customresourcedefinition.apiextensions.k8s.io "challenges.acme.cert-manager.io" deleted
        customresourcedefinition.apiextensions.k8s.io "clusterissuers.cert-manager.io" deleted
        customresourcedefinition.apiextensions.k8s.io "issuers.cert-manager.io" deleted
        customresourcedefinition.apiextensions.k8s.io "orders.acme.cert-manager.io" deleted
        serviceaccount "cert-manager-cainjector" deleted
        serviceaccount "cert-manager" deleted
        serviceaccount "cert-manager-webhook" deleted
        configmap "cert-manager-webhook" deleted
        clusterrole.rbac.authorization.k8s.io "cert-manager-cainjector" deleted
        clusterrole.rbac.authorization.k8s.io "cert-manager-controller-issuers" deleted
        clusterrole.rbac.authorization.k8s.io "cert-manager-controller-clusterissuers" deleted
        clusterrole.rbac.authorization.k8s.io "cert-manager-controller-certificates" deleted
        clusterrole.rbac.authorization.k8s.io "cert-manager-controller-orders" deleted
        clusterrole.rbac.authorization.k8s.io "cert-manager-controller-challenges" deleted
        clusterrole.rbac.authorization.k8s.io "cert-manager-controller-ingress-shim" deleted
        clusterrole.rbac.authorization.k8s.io "cert-manager-view" deleted
        clusterrole.rbac.authorization.k8s.io "cert-manager-edit" deleted
        clusterrole.rbac.authorization.k8s.io "cert-manager-controller-approve:cert-manager-io" deleted
        clusterrole.rbac.authorization.k8s.io "cert-manager-controller-certificatesigningrequests" deleted
        clusterrole.rbac.authorization.k8s.io "cert-manager-webhook:subjectaccessreviews" deleted
        clusterrolebinding.rbac.authorization.k8s.io "cert-manager-cainjector" deleted
        clusterrolebinding.rbac.authorization.k8s.io "cert-manager-controller-issuers" deleted
        clusterrolebinding.rbac.authorization.k8s.io "cert-manager-controller-clusterissuers" deleted
        clusterrolebinding.rbac.authorization.k8s.io "cert-manager-controller-certificates" deleted
        clusterrolebinding.rbac.authorization.k8s.io "cert-manager-controller-orders" deleted
        clusterrolebinding.rbac.authorization.k8s.io "cert-manager-controller-challenges" deleted
        clusterrolebinding.rbac.authorization.k8s.io "cert-manager-controller-ingress-shim" deleted
        clusterrolebinding.rbac.authorization.k8s.io "cert-manager-controller-approve:cert-manager-io" deleted
        clusterrolebinding.rbac.authorization.k8s.io "cert-manager-controller-certificatesigningrequests" deleted
        clusterrolebinding.rbac.authorization.k8s.io "cert-manager-webhook:subjectaccessreviews" deleted
        role.rbac.authorization.k8s.io "cert-manager-cainjector:leaderelection" deleted
        role.rbac.authorization.k8s.io "cert-manager:leaderelection" deleted
        role.rbac.authorization.k8s.io "cert-manager-webhook:dynamic-serving" deleted
        rolebinding.rbac.authorization.k8s.io "cert-manager-cainjector:leaderelection" deleted
        rolebinding.rbac.authorization.k8s.io "cert-manager:leaderelection" deleted
        rolebinding.rbac.authorization.k8s.io "cert-manager-webhook:dynamic-serving" deleted
        service "cert-manager" deleted
        service "cert-manager-webhook" deleted
        deployment.apps "cert-manager-cainjector" deleted
        deployment.apps "cert-manager" deleted
        deployment.apps "cert-manager-webhook" deleted
        mutatingwebhookconfiguration.admissionregistration.k8s.io "cert-manager-webhook" deleted
        validatingwebhookconfiguration.admissionregistration.k8s.io "cert-manager-webhook" deleted
        Deleted cert-manager

reference links on various add-ons - https://microk8s.io/docs/addons#heading--list

Starting and Stopping MicroK8s:

        microk8s stop
        microk8s start

Access Kubernetes using kubectl:

get nodes info

        kubectl get nodes
        
        ideelitserver2@ideelitserver2-PowerEdge-T40:~$ kubectl get nodes
        NAME                           STATUS   ROLES    AGE   VERSION
        ideelitserver2-poweredge-t40   Ready    <none>   25m   v1.29.4

get services info

        kubectl get services

        ideelitserver2@ideelitserver2-PowerEdge-T40:~$ kubectl get services
        NAME         TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)   AGE
        kubernetes   ClusterIP   10.152.183.1   <none>        443/TCP   26m
