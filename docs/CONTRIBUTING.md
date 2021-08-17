# Contributing to MGM

---

<p align="center">👍🎉  <strong> First off, thanks for taking the time to contribute! </strong>  🎉👍</p>

---

The following is a set of guidelines for contributing to the MoniGoMani Hyper Strategy and its modules, which are hosted in the [Rikj000 repository](https://github.com/Rikj000/MoniGoMani) on GitHub. These are mostly guidelines, not rules. Use your best judgment, and feel free to propose changes to this document in a pull request.

## Local development

### Git Commit Hook(s)

This project uses a set of git commit hooks to help us developers to write – *and more important, commit & push* – code mostly in the same fashion. These hooks are configured in `.pre-commit-config.yaml` and can be run on your dev machine by using an automated `pre-commit` integration.

See [Pre-commit](https://pre-commit.com) for usage and installation instructions.

### GitHub Action Workflows

GitHub Actions are used in order to run automated unit-tests against our code. These actions are triggered at push-events into main, development and feature/* branches. These actions are also triggered at every Pull Request so we all can see very quickly if something happened.

It can be quite handy to run a GitHub action workflow on your local machine. Well, [`act`](https://github.com/nektos/act) is your friend.

## Documentation

Special fields for the documentation (like Note boxes, ...) can be found [here](https://squidfunk.github.io/mkdocs-material/extensions/admonition/).

To test the documentation locally use the following commands.

``` bash
pip install -r docs/requirements-docs.txt
mkdocs serve
```

This will spin up a local server (usually on port 8000) so you can see if everything looks as you'd like it to.