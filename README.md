---
description: Easy Multiplayer Interactive Experiments in the Browser
---

# Introduction

{% hint style="success" %}
This documentation is for Empirica v2. If you want to see the documentation for Empirica v1, head over to [https://docsv1.empirica.ly](https://app.gitbook.com/o/-Lzv6Vw-a9xVOYgsBodE/s/-M-Cqf0McgfJZYwXisux/).

Note about the name `v2`. This is the second major version of Empirica after a complete re-write. But, confusingly, the main npm package for empirica v2 (@`empirica/core`) is currently numbered with `1` (i.e.: v1.x.y), because we're using a new package name. Sorry for the confusion.
{% endhint %}

Empirica is an open-source JavaScript framework for running multiplayer interactive experiments and games in the browser. Empirica makes it easy to develop and iterate on sophisticated designs in a statistically sound manner. It offers a unique combination of power, flexibility, and speed. Empirica is a powerful framework that facilitates the management of your games and experiments and is useful even for single-player research.

Empirica uses industry-standard open-source technologies (Go, GraphQL, Typescript, Javascript, React) Empirica provides a helpful structure to how your Games, Players, Rounds, and Stages interact. Furthermore, Empirica gives you an Admin Panel that makes organizing and running your Games for data collection easy and intuitive.

Empirica is the one method that provides enough flexibility to build any experiment while still being accessible and helpful to the researcher.

### Quick start

More details can be found on [#quick-start](./#quick-start "mention"). If you just want to get on with it:

```
curl -fsS https://install.empirica.dev | sh
empirica create myexperiment
cd myexperiment
empirica
```

### I want to use Empirica. Where do I start?

Visit the [Getting Started](getting-started/setup/) part of this documentation to get you started.

Follow our [first experiment tutorial](guides/tutorial-your-first-experiment/your-first-experiment.md).

To learn more about the parts of an Empirica app (e.g., what are Games, Rounds, and Players?) visit the [Concepts](overview/concepts.md) page.

### What skills do I need to use Empirica?

Empirica helps you build online apps for online research. As with many online tools, basic notions of HTML, CSS, and JavaScript will be helpful. Knowing a bit about React.js can also be beneficial, although you do not need to be an expert. There are many tutorials online for all the technologies mentioned here.

### Why should I use Empirica instead of just Node.js and React.js directly?

While Node.js and React.js are powerful tools, and you could build sophisticated experiments with them, Empirica makes building and managing your experiments much easier.

Notably, Empirica provides an Admin Panel that allows you to manage the conditions of your experiments (Treatments and Factors) and which Games are running, collecting data, or waiting for players.

Empirica does the heavy lifting in managing games, player connections, game life cycles, and more.

## What's new with Empirica v2?

Empirica v2 is a major departure from v1. It goes well beyond a few API changes since we have completely rebuilt Empirica from the ground up with new technologies. Here are a few key elements of the change:

* **New Features!** We have introduced a bunch of new capabilities. We are still working on the documentation, but here are a couple of examples of what's now possible:
  * Custom assignments: we have opened up the entire assignment flow. You can hook in anywhere and do all kinds of fun new assignment logic.
  * (Re-)Assignment to ongoing games: players can join ongoing games. They can also be reassigned between games.
* **Developer UX** Loading is fast; changes refresh instantly; we use standard npm libraries; the empirica command helps through the development process, etc. We have built a strong foundation and have only started the developer experience improvements.&#x20;
* **New Technologies** We are still using open-source technologies, but we no longer rely on Meteor.js. We have built a custom framework with a GraphQL server in Go. The backend is still on Node.js, though we no longer use Fibers, a deprecated Node.js technology used in Meteor.  And we are up to date with React v18+ on the frontend.
* **Open Architecture** We have purposefully centered our design on a Graphql API. We are not locked into one language or framework. We currently support a Node.js backend and a React front. But someone could develop a python backend to integrate with their existing libraries and a Flutter frontend to build a mobile app.

{% hint style="info" %}
To learn more about Empirica v2's differences and how to migrate to v2, see our v2 migration guide.
{% endhint %}
