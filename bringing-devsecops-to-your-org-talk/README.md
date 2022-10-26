# Bringing devsecops to your organization

By Nirmata / Kyverno

### Devsecops

1. Insert security into devops
2. make it easier to apply security best practices / as early as possible!

Kubernetes is built for devsecops!

It's declarative, users specify desired state as yaml and k8s controllers reconcilet he current state to the desired state.

### Why kubernetes can seem complex

1. Addresses concerns across different roles
2. its no opinionated
3. is not secure by default! 

So, who owns kubernetes security?

Vuln mgmt + Runtime (RBAC, pod security, net pol, data protection, image verification etc!)

This is where policies come in!

1. act as a contract
2. can prevent misconfig
3. automate key security concerns.

Kubernetes-native policies!

Why would you use a different language when you can use native policies

Build -> Apply policies in CI/CD -> Deploy -> Apply policies at admission controls -> RUN -> Apply policies via periodic scans!

### Kubernetes is not just about apps

1. git is the new system of record
2. k8s is the new system of engagement
3. native policies are required for agility, autonomy, and alignment

