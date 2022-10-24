# Securing access to k8s with zero trust

380,000 open k8s API Servers
84% K8s cluster accessible via the internet

### What is typically done?

1. SSH -> Bastion -> k8s cluster

2. SSH -> Jump Host -> SSH -> Bastion -> k8s cluster

3. kubectl -> VPN Gateway -> K8s cluster

### RBAC (Role based access)

SA -> Role binding -> Role -> Namespace

OR

SA -> ClusterRoleBinding -> ClusterRole -> PV Storage Class Cluster level resources

We don't want every developer who does not need access to the entire cluster, so they can only see what they want to see.

### What happens at scale?

10s or 100s of global k8s clusters? what do?

+ 100s of devs and ops personnel?

It's impossible to manage manually!

### What's the automation?

Reqs for zero trust access

1. Ability to remotely access "cloaked" clusters
2. Automated Ephemeral JIT, Lease privilege SA's
3. All Access Strongly Authenticated
4. Centralized Audit Trail of All access and activity

(Think of this like zscaler but for kubectl and kubeapi instead of webapps!)

### An open source solution!

Paralus - https://www.paralus.io/

Core capabilities:

1. create customer roles, users and groups
2. Changing and revoking perms
3. Access control + SSO 

How does it work?

Adds an agent on each cluster, it reaches out to the Paralus server via 443, and the nice thing is you get an audit trail of all the users kubectl commands, etc.


