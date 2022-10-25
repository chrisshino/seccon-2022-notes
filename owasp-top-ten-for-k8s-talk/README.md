# Introducing the OWASP Top Ten for K8s

https://github.com/OWASP/www-project-kubernetes-top-ten

### TOP 10!

1. Misconfigurations: tops the charts when it comes to security issues!
2. Supply chain security: a single container relys on hundreds of third-party components and deps making trust of origin at each phase extremely difficult!
3. Overly permissive RBAC Configs: enables fine grained access for users, groups and SA within k8s. It can be difficult to scope appropriately which opens up additional privileges! 
4. Lack of centralized Policy enforcement: security policies across multiple clusters, clouds and risk tolerances become unmanageable quickly! Use OPA or Kyverno 
5. Inadequate logging and monitoring: the k8s env has the ability to generate logs at a variety of levels from many diff components!
6. Broken Auth - K8s supports a number of auth mechanisms, however many are not suitable for production environments!
7. Missing network segmentation controls: Observer your active network traffic and compare that traffic to what is allowed baseed on your network policies! Consider alternatives such as service mesh or CNI plugins!
8. Secret management failures!
9. Misconfigured cluster components: The components are highly configurable. The kubelet running on each node are an example of a critical piece of infra that requires hardening! This is especially true in "DIY" clusters.
10. Outdated and vulnerable k8s components: make sure you are staying up to date!

Some questions to ask yourself:

Can containers run as root?
Can containers mount sensitive volumes / directories? Read or Read / Write?
Can Pods run in “Privileged” mode?
What policies (PSP, custom, OPA) are in place and for who?
How is authentication handled?
Is RBAC enforcing the principle of least privilege?
How are secrets being stored and retrieved? Rotated? Revoked?
Where do container images come from? Are images being validated?
How is network security being enforced? Can you audit these rules?
Are your hosts hardened? Monitoring in place?
Are you using Kubernetes Audit? Where are logs sent?
Ingress / LB inventory in place? What external IP addresses are available?
What happens if / when your application has an SSRF bug?
Have you performed a proper threat model of Kubernetes environments?
Third party products, tools, helpers? Are they secure?
