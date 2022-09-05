# Updating your experiment

Empirica in your experiment uses a command-line tool called `empirica` and
Javascript npm packages. The command-line tool allows you to create and run your
experiment, while the packages are the glue in your code that makes Empirica
work.

## Updating Empirica in your Experiment

You can update the packages in your experiment by running the following command
at the root of your experiment:

```
empirica upgrade
```

## Updating the Empirica Command

As new versions of Empirica become available, you might want to update the
`empirica` command-line tool. To do so, run:

```bash
curl https://install.empirica.dev | sh
```
