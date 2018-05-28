---
layout: post
title: GSoC - First two weeks
published: true
---

## Contributing

GitHub recognizes a special file in the repository called the CONTRIBUTING file. If you have a file named CONTRIBUTING with any file extension, GitHub will show Opening a Pull Request when a CONTRIBUTING file exists. when anyone starts opening a Pull Request [[1](https://git-scm.com/book/en/v2/GitHub-Maintaining-a-Project)].

We will make one for the highlyunstable branch called 'CONTRIBUTING.md', taking Hashicorp and Node.js as reference [[2](https://github.com/hashicorp/packer/blob/master/.github/CONTRIBUTING.md)] [[3](https://github.com/nodejs/node/blob/master/doc/guides/contributing/coc.md)].

This will serve as a guideline about how to contribute via pull request and issues, in an easy and orderly manner to Robocomp. 

## ReadTheDocs

The ReadTheDocs needs to be updated. So [this](https://robocomp.readthedocs.io/en/latest/) page can stop giving errors I'm changing the default version in ReadTheDocs, so the latest is `highlyunstable`.

I'm also adding support for Markdown syntax in the Sphinx documentation. This way the documentation only needs to be updated from Readme.md.

## Debian

I already created a Launhpad account [[4](https://launchpad.net/~mgbohorquez)]. The old Debian package is from [GSoC 2015](https://launchpad.net/~imnmfotmal). The student made a [tutorial](https://robocomp.github.io/web/gsoc/2015/nithin-murali/page8) explaining how to package Robocomp. All is left to do is push the new binary file to Launchpad.


##  Travis

As reported [here](https://github.com/travis-ci/travis-ci/issues/9080) the failures we have been having the last weeks might be a problem with Xenial. As a test we are temporarily switching to trusty. 

__Some hours later__

After changing to Trusty I got new errors, that I documented in an [issue](https://github.com/robocomp/robocomp/issues/153) in the Robocomp repository, with everything else I found.
