# Plumbing

This module contains utility scripts for voxpupuli admins to
do various management tasks.

## Travis secrets

To generate the list of encrypted blobs for puppet forge deployment:

```bash
./bin/puppet_encrypt_for_travis.sh $forge_password > share/travis_secrets
```

To generate the list of encrypted blobs for rubygems deployment:

```bash
./bin/rubygems_encrypt_for_travis.sh $rubygems_api_key > share/rubygems_travis_secrets
```

## Setting up a gem for rubygems deploys

Add the voxpupuli rubygems account to the owners list of the gem.

```bash
gem owner <gemname> -a krum.spencer+voxpupuli@gmail.com
```

## gpg

to decrypt:

```bash
./bin/decrypt_credentials.sh
```

to encrypt:

```bash
./bin/encrypt_credentials.sh
```

## syncing labels

Syncing labels can be done by using github-label-sync. The labels.json file
contains the labels to be synced

To sync a repository:

```bash
npm install -g github-label-sync
github-label-sync -a <GitHub token> <repository>
```

You can use -d for a dryrun to see what will be added and removed.

## Syntax Validation

We use <https://github.com/caarlos0/shell-ci-build> as a submodule in travis. This enables shellcheck and validates all \*,sh files. We probably should update it from time to time.

## Contribution

We currently require all commits in this repo to be signed with gpg, so please
configure your git client properly. Let us know if you need some help. We're
also reachable via our IRC channel `#voxpupuli` on freenode.￼
