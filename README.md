## Getting started

1. Set up a virtual environment
2. Install the Python deps: `pip install -r requirements.txt`
3. Install the JS deps: `cd themes/pydistrict/ && npm install && cd -`

## Developing locally

1. Load the virtual environment
2. Run `nikola build` to do an initial build
3. Run `nikola auto` to watch and serve on a local dev server.


## Adding an event

1. Load the virtual environment
2. To create a new:
  * main meetup, run `nikola new_post posts/{YYYY}/{MM}/{month_name}-meetup.md`, substituting in the year and month values.
  * project night, run `nikola new_post posts/{YYYY}/{MM}/{month_name}-project-night.md`, substituting the year and month values.
3. This will create a new markdown file for the event.
4. Open the markdown file in your editor of choice.
5. Give it some frontmatter. An example:
    ```
    <!--
    .. title: October Meetup
    .. slug: october-meetup
    .. date: 2020-10-18 21:17:39 UTC-05:00
    .. tags: meetup
    .. category: main-meetup
    .. link: https://www.meetup.com/pydistrict/events/274066238/
    .. event_time: 2020-10-27 18:00:00 UTC-05:00
    .. description: PyDistrict's October Meetup
    .. type: text
    -->
    ```
    * There is a required custom field, `event_time`, which corresponds to the start time of the meetup
    * The `category` must be one of `project-night` or `main-meetup` in order for the event to appear on
      the home page.


## Pushing to the world

1. Build the site: `nikola build && nikola build`
  * Two `build` commands are required due to nuances with Nikola's build
    process and compiled assets ([ticket](https://github.com/getnikola/nikola/issues/2495))
2. Publish to GitHub: `nikola github_deploy`
