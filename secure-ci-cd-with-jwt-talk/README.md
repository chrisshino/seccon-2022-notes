 # Secure CI/CD Using JSON Web Token (JWT)

 by: Gitlab

 ### Recommendations

 1. JWT + OpenID connect!

 most cloud platforms support OIDC!

 What does JWT look like?

 1. Short lived ID token
 2. Header, Body, Signature
 3. Body claim

### OIDC in devop workflow

1. Configure trust with OIDC with your provider (configure in GCP, AWS, ETC)
2. Generate and authenticate using JWT
3. Provide access token
4. Retrieve secrets

### Recap

1. secrets are typically stored in a dedicated mgmt solution.
2. secrets need to be integrated with your DevOps platform
3. Configure OIDC on target client
4. Setup your pipeline with JWT to access and retrieve secrets
5. Secrets securely stored and integrated with your existing DevOps tools


  