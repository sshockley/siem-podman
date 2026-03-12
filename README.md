# siem-podman
Basic SIEM deployed via Podman

# why
I've been trying to set up SIEM/managment/logging for my home "lab" to manage and monitor all the machines I seem to keep adding.  I've tried a few, but found some fatal flaws.

## Wazuh
* Managing rules is done via hand-editing an XML file in a container
* Vulnerability data includes dubious vulnerabilities that have never been patched, and you can't disable them

## UTMStack
* Only runs on Ubuntu, and I irrationally hate Ubuntu
* Were actually quite helpful when I had an issue (good)
* Lots of Dependabot PRs closed without applying
* AGPL so less chance of a rug pull (good)

## Security Onion
* Fairly polished, nice pre-made dashboards (good)
* Oracle Linux 9, which I don't... hate (good enough)
* Finally got it set up but it needed three machines, 12x cpu, 48GB RAM
* Configuration for things like firewall is done through a fiddly slow tree menu
* Everything is configured via Salt, so if you change anything it gets reverted
* Biggest resource hog was Salt, which is notable when you're running Elastic
* Absolutely no ARM support (fatal flaw)

I found ChiefGyk3d/siem-docker-stack, which looked perfect until I tried to get it running.  It's vibe coded and doesn't seem to actually work.  I'll probably use parts from that here, so he deserves some credit at least.

So, I'm making my own.  That's got to be easier than just using a product built by a team of professionals, right?
