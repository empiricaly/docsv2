# Updating your experiment

When new features or bug fixes are added to Empirica, you should try to upgrade to the latest version.

{% hint style="info" %}
&#x20;Before upgrading, you can head over to the [Empirica Release Notes](https://github.com/empiricaly/empirica/releases) to verify that there are no BREAKING CHANGES between your current and the latest versions.

To check the current version of your experiment, see [#check-the-current-version-of-your-experiment](updating-your-experiment.md#check-the-current-version-of-your-experiment "mention").
{% endhint %}

## Check the current version of your experiment

At the root of your experiment, run `empirica version`:

```
$ empirica version
Version: v1.0.0-rc.24
SHA:     bc4184e
Build:   169
Branch:  main
Time:    2022-12-28T08:21:58Z

Client:  1.0.0-rc.24
Server:  1.0.0-rc.24
```

## Updating Empirica in your Experiment

You can update the packages in your experiment by running the following command at the root of your experiment:

<pre><code><strong>$ empirica upgrade
</strong></code></pre>

Within your current experiment, this will upgrade both the `empirica` command and the npm packages used in `client/` and `server/`. This will **not** upgrade the `empirica` command globally. To upgrade the empirica command globally, see [#updating-the-empirica-command](updating-your-experiment.md#updating-the-empirica-command "mention")

## Change to a specific version in your experiment

If you need to upgrade (or downgrade) to a specific version of Empirica, you can pass the exact version like so:

```
$ empirica upgrade --version "v1.2.3"
```

You can also choose to only upgrade the command line or the npm packages individually with either:

```
$ empirica upgrade --commandOnly
$ empirica upgrade --packagesOnly
```

## Updating the Empirica command

To upgrade the `empirica` command globally (outside any existing experiment), run the following:

```
$ empirica upgrade --global
```
