# Project Boilerplate

This is the project boilerplate which will get you started. For any questions regarding the stack, please use our [#help](https://chasacademy.slack.com/messages/C61J8A678/#help) channel in Slack.

# Table of contents

<!--ts-->

* [Directory Layout](#directory-layout)
* [Quickstart](#quickstart)
* [Installation](#installation)
* [Usage](#usage)
  * [Bash Commands](#bash-commands)
* [Storybook](#storybook)

<!--te-->

## Directory Layout

```bash
./
├── /api                    # Directory for backend, see below for more detail (created when running /bin/install)
├── /client                 # Directory for frontend, see below for more detail (created when running /bin/install)
├── /client/src/elements    # Directory for smaller components
├── docker-compose.yml      # Defines Docker services, networks and volumes, do not touch unless you know what you are doing
└── README.md               # The file you are reading right now
```

**NOTE**: The `api` and `client` folders are in fact separate repositories (git submodules):

* Backend: [https://github.com/chas-academy/cobalt-api](https://github.com/chas-academy/cobalt-api)
* Frontend: [https://github.com/chas-academy/cobalt-client](https://github.com/chas-academy/cobalt-client)

This means when making changes to either you need to commit and push in the separate repositories.

## Quickstart

## Install and Start the Apps

1.  First download and install the [Docker Community Edition](https://www.docker.com/community-edition).
2.  From the root of the project, run `bin/install`, this will clone and install all the different apps, configure the database etc. – take a break while this runs.
3.  If the installation process is successful, both the API and client services shall be started and accesible locally at:

* API: <http://localhost:7770>
* APP: <http://localhost:7771>

# Usage

## Bash Commands

For easier access, you can run these following commands from the the `root` of the project.

| Command                                | Description                                                    |
| -------------------------------------- | -------------------------------------------------------------- |
| `./bin/install`                        | Clone the apps, build the Docker containers, and initialise db |
| `./bin/reinstall`                      | Delete the apps and run the installation process               |
| `./bin/update`                         | Pulls the latest changes from API and client                   |
| `./bin/start`                          | Start all the services (API, client, and database)             |
| `./bin/stop`                           | Stop all the services                                          |
| `./bin/console <container ID or Name>` | Access the terminal console of the API or client containers    |

Note: To manage separate Docker instance for API or client,
open another terminal console and change the project directory from `root` to `api` or `client` and run the commands above.

<!-- ### Database

| Command                         | Description                                               |
| ------------------------------- | --------------------------------------------------------- |
| `./bin/pg/resetdb`              | Drop and re-initialise database                           |
| `./bin/pg/migrate`              | Run new schema migration                                  |
| `./bin/pg/migrateundo`          | Revert the recent schema migration                        |
| `./bin/pg/seed <seed file>`     | Run specific data seed file with or without .js extension |
| `./bin/pg/seedundo <seed file>` | Revert the seed of specific data seed file                |
| `./bin/pg/psql`                 | Access the database console                               |

Note: Used `./bin/pg/psql <database container ID or Name>` to access the database console.
To run the commands above for separate API Docker instance, simply change the project directory from `root` to `api`. -->

# Storybook

### Starting storybook locally

1.  `cd client`
2.  `npm/yarn run storybook` - Runs at http://localhost:9009

<!-- # Gitflow

## Installation

##### OSX

`brew install git-flow-avh`

or

`port install git-flow-avh`

##### Linux

`apt-get install git-flow`

##### Windows

`wget -q -O - --no-check-certificate https://raw.github.com/petervanderdoes/gitflow-avh/develop/contrib/gitflow-installer.sh install stable | bash`

> You need wget and util-linux to install git-flow.
> Docs : <a href="https://github.com/petervanderdoes/gitflow-avh/wiki">click here</a>

## Usage - Gitflow

### Initialize

Start using git-flow by initializing it inside an existing git repository:

`git flow init`

You'll have to answer a few questions regarding the naming conventions for your branches.
It's recommended to use the default values.

## Features

#### Start new feature

Development of new features starting from the 'develop' branch.

Start developing a new feature with:

`git flow feature start <YOUR-FEATURE-NAME>`

This action creates a new feature branch based on 'develop' and switches to it

#### Finish up a feature

Finish the development of a feature. This action performs the following:

* Merges <YOUR-FEATURE> into 'develop'
* Removes the feature branch
* Switches back to 'develop'

`git flow feature finish <YOUR-FEATURE-NAME>`

#### Publish a feature

Publish a feature to the remote server so it can be used by other users.

`git flow feature publish <YOUR-FEATURE-NAME>`

#### Getting a published feature

Get a feature published by another user.

`git flow feature pull origin <YOUR-FEATURE-NAME>`

## Make a release

#### Starting a release

To start a release, use the git flow release command. It creates a release branch created from the 'develop' branch.

`git flow release start RELEASE [BASE]`

It's wise to publish the release branch after creating it to allow release commits by other developers. Do it similar to feature publishing with the command:

`git flow release publish RELEASE`

You can track the release with the follow command:

`git flow release track RELEASE`

#### Finishing up a release

Finishing a release is one of the big steps in git branching. It performs several actions:

* Merges the release branch back to 'master'
* Tags the release with its name
* Back-merges the release into 'develop'

`git flow release finish RELEASE`

Don't forget to push your tags with:

`git push --tags`

## Hotfixes

#### Starting a hotfix

Like the other git flow commands, a hotfix is started with

`git flow hotfix start VERSION [BASENAME]`

#### Finishing a hotfix

By finishing a hotfix it gets merged back into develop and master. Additionally the master merge is tagged with the hotfix version.

`git flow hotfix finish VERSION`

#### Commands

<img src="https://danielkummer.github.io/git-flow-cheatsheet/img/git-flow-commands.png" />

For more details about gitflow <a href="https://github.com/petervanderdoes/gitflow-avh/wiki/Installation">click here</a> -->
