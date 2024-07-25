# Docker.sigs

## Motivation

This repo serves as a location to upload and preserve detached signatures, which are then uploaded to the respective respository on dockerhub. This allows users to validate the the docker images they are using have been inspected, if not built, by the person who should've built it.

## Repos

(dashd)[dashd] Docker image hosting Dash Core.

## Steps to Sign

```
cosign sign --key path/to/priv/key/dashd.key --output-signature $(digest).cosig --upload=false docker.io/dashpay/dashd@sha256:$(digest)
```

## Steps to Validate

```
cosign verify --key=dashd.pub dashpay/dashd:20.1.1
```

