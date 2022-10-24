# Day in the life of a base image

By: Slim.ai

### Dockerslim + slim.ai Report

1. [A github project for container optimization](https://github.com/docker-slim/docker-slim)

They did a report where they pulled the most popular 165 public containers on dockerhub.

They scanned them using standard tools:

1. Xray -Dockerslim
2. SBOM - Syft, Anchore
3. Vulns - Grype, Anchore

Questions they asked:

1. Is the container going to be easy to use?
2. Is it efficient?
3. Is it safe?
4. Will it cause issues when I ship my app?

### What we learned?

1. by NOT slimming your containers, companies risk wasted time and decreased productivity in CI/CD
2. Look into the 2019 Darmstadt University research report 

A typical npm package contained abnormally large number of deps - an avg of 79 3rd party packages from 39 different maintainers.

3. Attack surface is MORE than a vuln count!

20% of all vulns are high/critical!


