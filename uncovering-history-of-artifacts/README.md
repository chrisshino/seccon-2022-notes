# Uncovering the history of your software artifacts

### Attestations 

1. tekton chains, slsa, etc all use in-toto!
2. spiffe creates trust!

### Discovery

1. A place where we have a gap is finding / querying 

example - If I only have a software artifact how do I find attestations created before the artifact existed?

maybe we can use context clues from attestations we can discover!

### Attestation graph!

1. My program -> Compile attestation (where it was build, who signed etc) -> then from their we can get Commit ID, project ID so we can get back to developer identity and such.

### Archivist!

An open source in-toto attestation graph service!

1. Indexes in-toto statements into a graph database
2. Exposes a GraphQL API to enable discovery of attestations
3. Uses in-toto subjects as graph edges

DEMO! 
