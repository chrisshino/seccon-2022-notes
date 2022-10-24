# Building images for the secure supply chain

By: Chainguard

742% average growth rate year over year in supply chain attacks

### Provenance is broken :(

1. Largely based on registry access
2. Cant prove where an image came from
3. Or it hasn't been tampered with

### Scanning is a horror show

1. Dont know what to do with all the vulns produced from scanners

How to gauge exposure? Log4j? commons text?

### But there is hope!

How to improve provenance?

1. Signing! sigstore, store alongside images in registry
2. keyless signing!

There was a cool live demo of how keyless signing works! Link it here later:

If you set it up with github actions it will do the OIDC on its own! so you just need to verify

Verify your signatures!

OPA, kyverno, etc!

### Silence scanner noise

1. Cut images down to minimum set of dependencies
2. Keep them updated
(FUTURE) Filter through VEX (vulnerability exchange?)

How do I cut down deps?

1. Smaller Images! (Alpine OR Debian-Slim)

Good, but plenty of stuff still. Updates can take time, first packages need to update then images need to be rebuilt!

Try using Google Container Tools Distroless!

What about Chainguard images???

Similar to GCT distroless, Easy to extend/customise with apko

Both base and application images WITH SBOMs included + continuosly updated.

### Vulnerability Exploitability eXchange

1. Way for vendors to say, yes we know scanners find CVE123 but this product is safe becasue X.
2. Cross referencing scanner reports and VEX

### Wrap up

1. Sign your images 
2. Reduce dependencies to get rid of scanner noise + keep images updated as possible
3. Exposure - Look into SBOM's!