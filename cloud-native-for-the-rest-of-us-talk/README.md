# Cloud native for the rest of us

By: VMware

### Security best practices

1. Less is more: Less code (Build vs Buy)
2. Fewer perms: avoid long lived secrets
3. Fewer dependencies: using smaller images (e.g. distroless)

### 4 C's of cloud native security

1. Code 
2. Container
3. Cluster
4. ...

### Managed >> DIY

1. Dont run it yourself 
2. Use a KAAS (GKE, EKS ,etc)

### Secure the control plane + Nodes

1. Restrict control plane access to just the K8s API Server
2. Dont get lazy with insecure-skip-tls-verify
3. TLS (there will be a talk "PKI The wrong way" <- watch it!!) 

https://github.com/tabbysable/pki-the-wrong-way

4. Lack of pod security
5. Access to cloud instance metadata (SSRF)

6. UPGRADE K8s! Pay attn: to deprecation cycles.

### Ingress example

1. v1.19 networking.k8s.io/v1beta1
2. v1.21 networking.k8s.io/v1
3. v1.19-v1.21 why not both??

### Isolating Network resources

1. Ingress/ Egress, Service Mesh (include mTLS), Going the extra mile: advanced netpol like [Cilium](https://cilium.io/)

### Managing secrets

1. Encryption at rest (K8s supports this)
2. Don't put secrets data directly in ConfigMaps: put them in secrets and then ref them with configmap

Even better use something like KMS, Vault, SealedSecrets, Kamus, SOPS

### User mgmt + perms

1. Authn (who are you?)
2. Authz (what are you allowed to do?)


For AUTHN: TLS certs, OIDC tokens (okta), SA/Client certs, etc.

keep token short lived
for humans: TLS, OIDC, Service account, etc

Robots: use SA

[SPIFFE.io](https://spiffe.io/)

FOR AUTHZ: 

K8s API server authorization modes:

1. Node
2. ABAC (Attribute based access control)
3. RBAC (Role based access control)
4. Webhook (Allows you to use hook into an existing system)

### Audit your RBAC

1. `kubectl can-i --list`
2. `kubectl who-can` (by aqua security!)

Perms can be cluster wide OR by namespace

### Software supply chain

1. your factory is your CI/CD pipeline (Secure it!)
2. commit access to source repos?
3. it's dependencies?

Harden every link in your chain!

1. SIGN EVERYTHING (with sigstore)
2. is it from your source repo? can only authorized people push to i
3. is the build system trusted? ( do we use ephemeral builds? )

Vuln scanning!

1. Clair, Trivy

Use Policy enforcement!

1. OPA or gatekeeper!
