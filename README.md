# heroku-buildpack-nlp-discovery
====

Add an NLP based task discovery integration to amitree build.

## Usage

1. Add the buildpack to your Heroku app:

    ```
    $ heroku buildpacks:add TODO: move the repo into Amitree organization
    ```

    Keep in mind that the buildpack order is important. If you'll specify this buildpack after your default one (e.g. `heroku/nodejs`) it'll not work. See [https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app](https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app) for details.

2. Set `BUILDPACK_SSH_KEY` to the private SSH key to access amitree/nlp_discovery repository:

    ```
    $ heroku config:set BUILDPACK_SSH_KEY="$(cat ~/.ssh/id_rsa)"
    ```

	The buildpack will save the SSH key to your build at `~/.ssh/id_rsa`.


2. Set `NLP_DISCOVERY_REPO` to clone the repo by using the given SSH key:

    ```
    $ heroku config:set NLP_DISCOVERY_REPO=$REPO_URL
    ```
