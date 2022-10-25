# Detecting threats in github with falco

By: Sysdig

### Are your repos safe?

It's a prime target for attacks!

Things that can go wrong:

1. Pushing secrets into a repo
2. Running actions with miners
3. Mistakenly publishing a private repo

### How can we detect and protect from these threats?

USE FALCO!

Traditionally to protect k8s resources, but now you can protect github too!

it's a runtime security tool and ties into your github, then you simply write some rules in a yaml file to tell it what to check for.

You can also create github rules for other stuff like info on if someone starred your repo!