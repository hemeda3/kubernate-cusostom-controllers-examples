# tgik-controller

Example controller for TGIK talk.

Covers:
- Controllers
- Getters
- Informers
- Listers
- Cache Synchronisation
- Rate Limiting Queues & Workers

Added by me:
- Ingress Controller
- Pod Controller
- Service Controller 
## Under development
Integrated X-Loadbalancer (nginx/...) with Ingress Controller
- will watch add/update/delete ingress object and print the ingress PATH + targeted Servcie + targeted service port
my goal is to create load balancer like so that I can deploy service and I can access it from localhost
example:-
I deploy shopping cart app in k8 platform (pods+service), and I can access it from my localhost/shopping
and my ingress controller IC, should be smart enough to redirect any localhost/shopping to my services
When I do remove/add pods or delete and add or reconfigure service(node ports changing) the IC should be smart enough
to figure what is the new service port.
in short as you know when we create servcie with NodePort type, the port may changes depends on the range we gave at begining of kubeadm init , my IC should find out the new port and link it the ingress and do reverse-proxy it to localhost


## Videos
This sample repository was developed and explained across three episodes of the [TGI Kubernetes](https://www.youtube.com/watch?v=9YYeE-bMWv8&list=PLvmPtYZtoXOENHJiAQc6HmV2jmuexKfrJ) YouTube Series.
- [TGI Kubernetes 007: Building a Controller](https://www.youtube.com/watch?v=8Xo_ghCIOSY)
- [TGI Kubernetes 008: Continuing the Controller](https://www.youtube.com/watch?v=fWkK-zsFtlU)
- [TGI Kubernetes 009: Finishing the Controller](https://www.youtube.com/watch?v=wqhKCiGsf1Y)


## Ideas/code stolen from...
This repo vendors in client-go along with all of the appropriate dependencies.  The procedure followed is described by @ncdc in this [blog post](https://blog.heptio.com/straighten-out-your-kubernetes-client-go-dependencies-heptioprotip-8baeed46fe7d).

The docker build makefile and such was taken from https://github.com/thockin/go-build-template.
