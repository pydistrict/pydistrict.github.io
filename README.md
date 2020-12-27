## Getting started

1. Set up a virtual environment
2. Install the Python deps: `pip install -r requirements.txt`
3. Install the JS deps: `cd themes/pydistrict/ && npm install && cd -`

## Devloping locally

1. Load the virtual environment
2. Run `nikola build` to do an initial build
3. Run `nikola auto` to watch and serve on a local dev server.

## Pushing to the world

1. Build the site: `nikola build && nikola build`
  * Two `build` commands are required due to nuances with Nikola's build
    process and compiled assets ([ticket](https://github.com/getnikola/nikola/issues/2495))
2. Publish to GitHub: `nikola github_deploy`
