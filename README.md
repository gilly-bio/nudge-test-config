# nudge brain: Tinfoil configuration

This repository holds the measured configuration of the nudge brain on Tinfoil Containers, `tinfoil-config.yml`.
Tinfoil's two release workflows release it: for each tag, they measure the configuration and publish a Sigstore
bundle, so anyone can check what an instance at that tag runs.

- **The beta's repository** has only `v1.2.3` tags: releases a device may trust. It does so only once the release has
  been public for 24 hours, and only if it isn't on the signed revocation list.
- **The test repository** has only `t1.2.3` tags, which run test data only. A device never trusts them. The two are
  kept apart so a test release never becomes the beta's latest.
- **The configuration is rendered** from a values file by the brain's deploy tool. Don't edit it by hand.
- **Nothing here is secret.** The brain's own keys reach the enclave from our keyserver at boot, and only once it has
  checked the release.
