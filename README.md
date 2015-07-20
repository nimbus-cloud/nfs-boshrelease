# BOSH Release for nfs

## Usage

To use this bosh release, first upload it to your bosh:

```
bosh target BOSH_HOST
git clone https://github.com/compozed/nfs-boshrelease.git
cd nfs-boshrelease
bosh upload release releases/nfs-1.yml
```

For [bosh-lite](https://github.com/cloudfoundry/bosh-lite), you can quickly create a deployment manifest & deploy a cluster:

```
templates/make_manifest warden
bosh -n deploy path_to_your_stub_yml
```


### Development

As a developer of this release, create new releases and upload them:

```
bosh create release --force && bosh -n upload release
```

### Final releases

To share final releases:

```
bosh create release --final
```

By default the version number will be bumped to the next major number. You can specify alternate versions:


```
bosh create release --final --version 2.1
```

### Publish release on Github

pre requirements:

```
  go get github.com/aktau/github-release
  export GITHUB_TOKEN=your-github-token #see: https://help.github.com/articles/creating-an-access-token-for-command-line-use/
```

Generate new final release with tags and tgz.




After the first release you need to contact [Dmitriy Kalinin](mailto://dkalinin@pivotal.io) to request your project is added to https://bosh.io/releases (as mentioned in README above).
