# Creating your experiment

Once you have finished setting up Node and Meteor, [as per our setup guide](setup/), you can use `empirica create` to create your experiment.

Simply run the following command, where `my-experiment` is your experiment name (no spaces or uppercase letters):

```bash
empirica create my-experiment
```

It will create a directory called `my-experiment` inside the current folder.
Inside that directory, it will generate the initial
[structure](broken-reference) and install the transitive dependencies.

Once the installation is done, open your project folder:

```bash
cd my-experiment
```

You can now read more about the running your experiment, the structure of an
Empirica experiment, and you can try our tutorial:

{% content-ref url="quick-test.md" %}
[quick-test.md](quick-test.md)
{% endcontent-ref %}
