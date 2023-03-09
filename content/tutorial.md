+++
author = "Leonhard Applis"
title = "Tutorial"
date = "2022-12-30"
description = "How to use HasBugs"
tags = [
    "Tutorial",
    "Resources"
]
+++

Thanks for having a look. 
Depending on what you want to do, we have different formats provided:

- [A Repository for docker images](https://github.com/orgs/ciselab/packages?repo_name=HasBugs)
- [Datapoints as JSON](/bugs)
- ["manifested" Haskell Projects](https://github.com/ciselab/HasBugs)

An important point is our naming: 
We have the bugs in different **versions** - `buggy, tested & fixed`. 
These all refer to the same project at different commits. 
`Buggy` is the commit at which the fault was present. As tracking faults back to introduction is very difficult, we assume the commit before the patch is buggy. 
Buggy versions do not necessarily have failing tests --- that is the reason for the `Tested` version. The tested version still has the behaviour of the buggy version, with the tests from the fixed version added to the CI. Hence, the build of the tested version fails. 
Lastly, the `fixed` version has a passing CI and the corrected behavior. 

We cover the above-mentioned parts in order, and at the end is a short tutorial how you would go about contributing a datapoint.

## Docker Images

Haskell Compilation takes a long time. 

Thus we didn't want to put the burden of long compilation times on the user (you). 
The provided docker images are additional docker images added to the repositories, running the build process at its current stage (buggy, tested or fixed).
We tried to compensate the long build times by separating *build* and *tests* in the container to give you a tradeoff in time for memory and downloads. 

If you want to run a project, you can do so by running: 

```sh
docker pull ghcr.io/ciselab/hasbugs/shellcheck-1:tested-1.0.0
docker run ghcr.io/ciselab/hasbugs/shellcheck-1:tested-1.0.0
```
*last checked docker version: `20.10.21, build baedalf`*

This should work for all datapoints. Just adjust the bug-id and version (`buggy`,`tested` or `fixed`). The available bug ids are visible on this website. 

In case you want to alter the project and re-run the CI, you will have to first manifest the datapoints (see below), alter them and run their respective docker build. 

*Note*: The project will require a lot of disk space for all docker images (~10gb/image). Please be careful. 

## Datapoints as JSON

This should be the easiest one - for you to browse through the datapoints you can just [see the data-showcase](/bugs). 

Other than that, all datapoints are found in [the repository](https://github.com/ciselab/HasBugs) sorted as single *json*s in the folder *references*. 
A top-level json is also provided that contains all datapoints as a list.  

## Manifested Datapoints 

To manifest the datapoints, you first need to pull [the repository](https://github.com/ciselab/HasBugs). 

The original datapoints are found under */references/project/id*, and can be manifested with the shell files provided in the respective directory. 
To get the buggy version of cabal-1, you can do the following: 

```sh
cd ./references/cabal/1
bash get-buggy.sh
```

This will (if one does not already exist) create a toplevel folder */data* that contains the projects original code. 
The items in */data* are sorted as */data/bug-id/version*, see below for an example repository after datapoints have been pulled.

If you feel like it, you can pull all data by looking into */tools* and run *get-all-datapoints.sh*. 

```
./HasBugs
├── README.md
├── data
│   ├── cabal-1
│   │   ├── buggy
│   │   │   ├── ...
│   │   │   ├── HASBUGS_DOCKERFILE
│   │   │   ├── HASBUGS_DOCKERFILE.dockerignore
│   │   │   ├── LICENSE
│   │   │   ├── Makefile
│   │   │   ├── README.md
│   │   │   ├── ...
│   │   │   └── weeder.dhall
│   │   ├── fixed
│   │   │   ├── AUTHORS
│   │   │   ├── CONTRIBUTING.md
│   │   │   ├── ...
│   │   │   └── weeder.dhall
│   │   └── tested
│   │       ├── AUTHORS
│   │       ├── CONTRIBUTING.md
│   │       ├── Cabal
│   │       ├── ...
│   │       └── weeder.dhall
│   └── hls-1
│       ├── buggy
│       │   ├── CITATION.cff
│       │   ├── CODEOWNERS
│       │   ├── CODE_OF_CONDUCT.md
│       │   ├── ChangeLog.md
│       │   ├── ...
│       │   └── test-logs
│       ├── fixed
│       │   ├── CITATION.cff
│       │   ├── CODEOWNERS
│       │   ├── ...
│       │   └── test-logs
│       └── tested
│           ├── ...
│           └── test-logs
├── references
│   ├── cabal
│   │   ├── 1
│   │   │   ├── HASBUGS_DOCKERFILE
│   │   │   ├── HASBUGS_TEST.patch
│   │   │   ├── datapoint.json
│   │   │   ├── get-buggy.sh
│   │   │   ├── get-fixed.sh
│   │   │   ├── get-tested.sh
│   │   │   ├── metadata.config
│   │   │   └── run-tested.sh
│   │   ├── HASBUGS_DOCKERFILE
│   │   ├── bug-work.md
│   │   ├── create-bug.sh
│   │   ├── get-repo.sh
│   │   └── metadata.config
│   ├── hls
│   │   ├── 1
│   │   │   ├── HASBUGS_DOCKERFILE
│   │   │   ├── HASBUGS_TEST.patch
│   │   │   ├── datapoint.json
│   │   │   ├── get-buggy.sh
│   │   │   ├── get-fixed.sh
│   │   │   ├── get-tested.sh
│   │   │   ├── metadata.config
│   │   │   └── run-tested.sh
│   │   ├── [ Other Bug IDs ... ] 
│   │   ├── HASBUGS_DOCKERFILE
│   │   ├── bug-work.md
│   │   ├── create-bug.sh
│   │   ├── get-repo.sh
│   │   └── metadata.config
│   └── [Other Repositories ...]
└── tools
    ├── ...
```

By default, we keep *.git* folders from the projects, as some need it to function (they use caching, very interesting). 
You can change this behaviour by setting the `$remove_history` flag in [get-repo.sh](https://github.com/ciselab/HasBugs/blob/main/tools/get-repo.sh) to what you prefer. Not having the git history will save you a massive amount of disk space.  

## Adding a Datapoint

**Adding a datapoint** to an existing project is rather easy. 

First, you should prepare your contribution by looking for the following key-points: 

- Issues & PRs
- Creating a patch with the test 
- Description of the bug
- The commit that visibly fixed the bug (to find bug-locations)

A description of how to make the test-patch is given in [a short readme file](https://github.com/ciselab/HasBugs/blob/main/tools/git-helpers.md). 

With these items ready, you can run `/references/repository/create-bug.sh`. 
It will ask you some questions in the command line and create the files accordingly. 
The only thing that has to be adjusted afterwards are the *datapoint.json* for the bug-location and maybe the Dockerfile.

Usually the existing Dockerfile works and does not need to be changed. 
In case it doesn't work, the best way to fix it is by inspecting the projects README and cabal/stack files at the time of commit.

**Adding a new Project** consists of a few more steps: 

First, you need to run the toplevel `/setup.sh` to *load* more shell files into your command line. Once this worked, you can create a new project by running `create-repo`. It will ask you for a bit of information, such as repository url, build- & test-frameworks and ghc versions. 

Next, you should setup a promising Dockerfile to run the project's build. We recommend you first create your first datapoint, and then re-use the docker image that worked there. 

We also encourage you to write a short `notes.md` for the repository that contains any information particularly important, e.g. build times and image size. 

**Contributing** your bug is highly appreciated! We are looking forward to your PR. Do not hesitate to @ us, or to [open issues](https://github.com/ciselab/HasBugs/issues). 
We are, however, dreadfully busy people so it can take a bit until we come back to you. 
Also, it can be that we change some elements of the datapoint before merge, e.g. the wording of the bug-issue or categories, to fit with existing granularity.
