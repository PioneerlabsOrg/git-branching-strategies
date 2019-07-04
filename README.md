# Git Branching Strategies

## Git Flow

- master — this branch contains production code. All development code is merged into master in sometime.
- develop — this branch contains pre-production code. When the features are finished then they are merged into develop.
- During the development cycle, a variety of supporting branches are used:
- feature-* — feature branches are used to develop new features for the upcoming releases. May branch off from develop and must merge into develop.
- hotfix-* — hotfix branches are necessary to act immediately upon an undesired status of master. May branch off from master and must merge into master anddevelop.
- release-* — release branches support preparation of a new production release. They allow many minor bug to be fixed and preparation of meta-data for a release. May branch off from develop and must merge into master anddevelop.

The problem of Git flow is the complexity introduced by the hotfix and release branches. 
These branches can be a good idea for some organizations but are overkill for the vast majority of them. 
Nowadays, most organizations practice continuous delivery, which means that your default branch can be deployed. 

![PlantUML model](https://github.com/PioneerlabsOrg/git-branching-strategies/blob/master/git-flow.png)

## GitHub Flow

- master — anything in the master branch is deployable

Github Flow promotes short lived feature branches and pull requests.
When a feature is completed we open pull request.
Someonelse reivews the pull rewquest and then we can merge back to master
Once the feature ha been merged back to master we should deploy immediatly.
it is friendly for the Continuous Delivery and Continuous Integration.

The problem of GitHub flow is that is not adequate when it needs the release plans.
It isn’t recommended when multiple versions in production are needed


## GitLab Flow

GitLab Flow is similar to the GitHub Flow apart that they promotes enviroments and release branches.

- master — this branch contains the development code. All development code is merged into master in sometime.
- feature-* — feature branches are used to develop new features for the upcoming releases. May branch off from master and must merge into master.
- enviroment-* — enviroments branches are branhed out from master.
- release-* — release branches support preparation of a new production release. They allow many minor bug to be fixed and preparation of meta-data for a release. May branch off from develop and must merge into master anddevelop.


It is more complex that the GitHub Flow.
It can become complex as Git Flow when it needs to maintain multiple version in production.

## One flow

One flow is the same as Git Flow apart that they don't use develop branch.

## Trunk-flow.

Trunk based development consists in pushing everything to master and release from that continuosly.
Pair programming is often used instead of Pull Requests.


## Toggles Flow Stream

Toggles Flow Stream promotes feature flag development instead of feature branches. 
While Feature branches are still possible, Toggles flow stream allows feature driven trunk based development.
The main difference from trunk base development is that we can release different features in different enviroments at any time without having to deal with the code.

## Toggle Flow Map

Toggle Flow Map is the same as Toggles Flow Stream apart that Toggles releases config maps instead of streams.
This means that the application will consume the features from the config map instead of from the Toggles Stream.



