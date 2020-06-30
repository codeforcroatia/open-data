# Contributing

Hi there! We're thrilled that you'd like to contribute to this project. Your help is essential for keeping it great.

Contributions to this project are [released](https://help.github.com/articles/github-terms-of-service/#6-contributions-under-repository-license) to the public under the project's open source license.

Please note that this project is released with a Contributor Code of Conduct. By participating in this project you agree to abide by its terms.

## How to contribute

We are really glad you're reading this, because we need volunteer developers to help this project come to fruition.

If you haven't already, come find us on Slack ([CodeForCroatia](https://codeforcroatia.slack.com)) or Discourse forum ([Code for Croatia Diskurs](https://diskurs.codeforcroatia.org)). We want you working on things you're excited about.

### Gather open data

You can embark on a quest to get open data on multiple ways:
- ask a government to provide you data they have and you need (see [ImamoPravoZnati](https://imamopravoznati.org) to request datasets for reuse in Republic of Croatia)
- scrape public data from government webpages
- be creative

### Structure data and create metadata descriptions

Each dataset with it's versions is gathered in a single directory under root of this repository, and contents of this directory is datasets and it's versions and also metadata to descrive datasets:
- **dataset_name**
  - dataset.csv
  - dataset.json
  - dataset-year-2010.csv
  - dataset-year-2011.csv
  - datapackage.json
  - README.md

Each dataset directory will have single README.md and single datapackage.json to describe a datasets in this directory. README.md is metadata standard used to publish your dataset in [JKAN - Open Data Portal](https://data.codeforcroatia.org/), and datapackage.json is a Frictionless Data Specification.

You can create and verify your datapackage.json at [create.frictionlessdata.io](https://create.frictionlessdata.io). For more info about Frictionless Data please visit [frictionlessdata.io](https://frictionlessdata.io).

Once files and correctly structured, proceed with next step and create a pull request.

## Submitting a pull request

0. Fork and clone the repository
0. Create a new branch: `git checkout -b my-branch-name`
0. Push to your fork and submit a pull request
0. Pat your self on the back and wait for your pull request to be reviewed and merged.

Here are a few things you can do that will increase the likelihood of your pull request being accepted:

- Follow standards for style and code quality.
- Write tests.
- Keep your change as focused as possible. If there are multiple changes you would like to make that are not dependent upon each other, consider submitting them as separate pull requests.
- Write a [good commit message](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html).

## Resources

- [How to Contribute to Open Source](https://opensource.guide/how-to-contribute/)
- [Using Pull Requests](https://help.github.com/articles/about-pull-requests/)
- [GitHub Help](https://help.github.com)
