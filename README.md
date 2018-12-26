[![Build Status](https://travis-ci.com/SRSMiJourney/mijourney.dashboard.svg?token=2YsBN6KDFsrvVQwoHULo&branch=development)](https://travis-ci.com/SRSMiJourney/mijourney.dashboard)

# masse.ios
Masse iOS client application

### Table of Contents  
1. [Branch Management](#branch-management)
2. [Creating Builds] (#creating-builds)
3. [Releases](#releases)
4. [Versioning](#versioning)


## Branch Management

Management of our branches will be almost identical across all of our repositories which makes following the below definitions of utmost importance. Each branch we create has a well-defined name and purpose on how it will both impact the project as well as be presented back into our code base.

#### master
> Code that reflects what is currently deployed onto production and/or the App Store.

#### develop
> Branch from master.

#### feature/*
> Branch from develop that will contain a full set of changes to accommodate a new feature.

#### release/*
> A collection of `feature/*` branches that identify with a particular planned release version.

#### bugfix/*
> Branch originating from, and to be released with, next target `release/*` branch

#### hotfix/*
> Branch from master with the purpose of being released to production immediately to resolve any critical show-stopper issue(s).


## Creating Builds

```fastlane build_development --env Masse-Dev```

## Releases

For every application release that is made a process should be followed to allow others to correctly identify previous test and release versions. Below is a guide that should be followed for each app deployment that is made.

#### QA Release
1. Commit code to appropriate branch (e.g. `release/*`)
2. Produce build at an incremented number from previous (e.g. `1.4 (1)` to `1.4 (2)`)
3. Tag as `QA Release 1.4 (1)` on Github

#### TestFlight Release
1. Commit code to appropriate branch (e.g. `release/*`)
2. Produce build at an incremented number from previous (e.g. `1.4 (1)` to `1.4 (2)`)
3. Tag as `TF Release 1.4 (1)` on Github

#### App Store Release
1. Commit code to appropriate branch (e.g. `release/*`)
2. Produce build at expected release version (e.g. `1.4`)
3. Tag as `Store Release 1.4` on Github

> NOTE: Build increment value should always resemble its intended release number and the actual internal build number `Bundle Version` should be incremented originating from 0 for each new major or feature release.

## Versioning

Allowing us to keep all of our code cleanly represented, our versioning system allows everyone to quickly identifiy the purpose of each released version. Below we cover what each section of the version identifies, and in what use cases those numbers should be appropriately incremented.

##### Format

`{ Major }` . `{ Minor }` . `{ Hotfix }`


#### Major
> Change occurs when a large change has been made to the project such as a significant code rewrite and/or refactor, or a large UI overhaul to the users experience.

#### Minor
> Change occurs on planned releases of new features presented into the application.

#### Hotfix
> When a quick bug fix requires expedited release to compliment an existing feature release. Ideally these increments will be utilized minimally, as hotfixes are intended only for urgent issues that require immediate production patching.

### Examples

`1.0` - Initial major launch

`1.1` - New feature release

`1.1.1` - Hotfix release
