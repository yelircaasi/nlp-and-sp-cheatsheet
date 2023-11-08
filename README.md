# nlp-and-sp-cheatsheet

Source for the [NLP and SP Cheatsheet](https://nlp-and-sp-cheatsheet.readthedocs.io/en/latest/).
Still a work in progress, and I plan to work more in it toward the end of the year.

## Contributing

To contribute, fork this repo and clone your fork. These instructions are fairly detailed - I'm not
trying to insult the intelligence of experienced developers; I'm trying to make this accessible to
beginners. We all start somewhere, and everyone is welcome.

This project uses Poetry for Python dependency management, which has a nice dependency resolver and
dependency locking functionality, while allow managing the virtual environment. This makes
collaboration easier because it makes the development environment reproducible.

It allow uses pre-commit to enforce good practices. Be sure to follow
[Conventional Commits](https://www.conventionalcommits.org) guidelines.

Assuming a working installation of [Python 3.11 or newer](https://github.com/pyenv/pyenv) and
[pipx](https://pypa.github.io/pipx/installation/), the following commands are all you need to build
the docs:

```sh
# install poetry if you do not already have poetry installed;
# pipx is a tool for cleanly installing python command-line tools inside a virtual environment
pipx poetry

git clone git@github.com:yelircaasi/nlp-and-sp-cheatsheet.git
cd nlp-and-sp-cheatsheet

# enter virtual environment and install dependencies without installing the current project
poetry shell
poetry install --no-root

# build docs; see ./docs/Makefile for details
cd docs
make html
```

Before changing something, be sure to fetch from upstream. Add the upstream repo if you have not
already done so.

```sh
git remote add upstream https://github.com/yelircaasi/nlp-and-sp-cheatsheet.git
git fetch upstream
```

Once you have made your changes, be sure to run [pre-commit](https://pre-commit.com/). Usually I
run it once before committing to catch the errors and make changes so that it doesn't raise any
objections when I actually commit. Most of the hooks automatically make changes, especially the
ones likely to find problems in the changes you have made.

```sh
# installation only needed the first time, but not catastrophic to re-run
pre-commit install
git add .
pre-commit run --all-files

# don't copy the next line verbatim, of course :)
git commit -m "{{commit type (feat|fix|chore|test)}}: {{informative and concise commit message}}"
git push
```

Once you have pushed your changes, go to Github and open a pull request, where your contribution
will be reviewed by a maintainer. Thanks for getting involved!
