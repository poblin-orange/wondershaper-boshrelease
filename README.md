# BOSH release for wondershaper

This BOSH release and deployment manifest deploy a cluster of wondershaper.

## Usage

This repository includes base manifests and operator files. They can be used for initial deployments and subsequently used for updating your deployments:

```plain
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=wondershaper
git clone https://github.com/cloudfoundry-community/wondershaper-boshrelease.git
bosh deploy wondershaper-boshrelease/manifests/wondershaper.yml
```

If your BOSH does not have Credhub/Config Server, then remember `--vars-store` to allow generation of passwords and certificates.

### Update

When new versions of `wondershaper-boshrelease` are released the `manifests/wondershaper.yml` file will be updated. This means you can easily `git pull` and `bosh deploy` to upgrade.

```plain
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=wondershaper
cd wondershaper-boshrelease
git pull
cd -
bosh deploy wondershaper-boshrelease/manifests/wondershaper.yml
```
