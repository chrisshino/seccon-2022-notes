# How’s Your Supply Chain with Your Insecure OSS Ingestion?

By: Citi

### Supply chain landscape

1. Are you making sure you should use the library before using it?
2. Do you know where your libraries are coming from?

NPM 2% of the packages are doing malicious activities! 

### What signals should we look at in libraries?

1. Fail on signature fails, sanctioned country, malicious code detected, malicious actor detected.

Question - Should we justify why we bring in a library? Should everything be built from source?

### Evolution && Tooling

SBOM, SLSA, VEX, KEV

These now start to enable automation & scale

A common flow:

1. PURL request -> Lookup PURL policy/metadata -> PURL Evaluation -> Scan Evaluation

** Another cool idea ** 

Bring in a library in a sandbox environment and then run it to see if it does anything dicey like run an install script of some sort.

DEMO with NPM ecosystem / React.

