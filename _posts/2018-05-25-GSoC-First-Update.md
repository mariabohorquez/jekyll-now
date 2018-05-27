---
layout: post
title: GSoC - First two weeks
published: true
---

## Contributing

GitHub recognizes a special file in the repository called the CONTRIBUTING file. If you have a file named CONTRIBUTING with any file extension, GitHub will show Opening a Pull Request when a CONTRIBUTING file exists. when anyone starts opening a Pull Request [[1](https://git-scm.com/book/en/v2/GitHub-Maintaining-a-Project)].

We will make one for the highlyunstable branch called 'CONTRIBUTING.md'. We'll make one taking Hashicorp and Node.js as reference [[2](https://github.com/hashicorp/packer/blob/master/.github/CONTRIBUTING.md)] [[3](https://github.com/nodejs/node/blob/master/doc/guides/contributing/coc.md)].

This will serve as a guideline about how to contribute via pull request and issues, in an easy and orderly manner to Robocomp. 

## ReadTheDocs

The ReadTheDocs needs to be updated. So [this](https://robocomp.readthedocs.io/en/latest/) page can stop giving errors I'm changing the default version in ReadTheDocs, so the latest is `highlyunstable`.

## Debian


##  Travis

As reported [here](https://github.com/travis-ci/travis-ci/issues/9080) the failures we have been having the last weeks might be a problem with Xenial. As a test we are temporarily switching to trusty. 

After changing to Trusty I realizad some things, that I documented in an [issue](https://github.com/robocomp/robocomp/issues/153) in the Robocomp repository, with everything else I found.
