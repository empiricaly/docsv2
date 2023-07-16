# Beginner Experiment: Prisoner's Dilemma

In this beginner-level tutorial, you will build a simple two-player experiment from scratch, based on the classic [“Prisoner’s Dilemma”](https://en.wikipedia.org/wiki/Prisoner's\_dilemma) game. This tutorial introduces the major building blocks of an Empirica experiment, including players, rounds, stages, and UI design.&#x20;

This tutorial can be used independently or as a supplement to the Empirica workshop and tutorial (to be) filmed at the International Conference for Computational Social Science in July 2023.

### How social scientists can use this tutorial

This tutorial provides detailed instructions that will help you get started building your first experiment in Empirica. The tutorial doesn't assume any prior knowledge of Javascript or React, although some experience with programming will be helpful.

Many experiments can be built up from this basic foundation with small changes to the way information is presented or the choices participants are presented with. The goal of this tutorial is to help you become more comfortable with Empirica and understand how to translate your experiments from ideas to tangible code.

For resources that can help you become a more capable developer, see:&#x20;

{% content-ref url="../../resources/javascript-and-react.md" %}
[javascript-and-react.md](../../resources/javascript-and-react.md)
{% endcontent-ref %}

{% content-ref url="../../resources/helpful-linux-commands.md" %}
[helpful-linux-commands.md](../../resources/helpful-linux-commands.md)
{% endcontent-ref %}

### How software developers can use this tutorial

If you are a software developer and comfortable using React, JavaScript, CSS, etc., this tutorial will help you quickly understand the basic structure of an Empirica experiment. This tutorial may act as a helpful example to refer to when implementing other experiments that your team wants to explore. To get more familiar with the Empirica conceptual model, see:

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

## About the experiment

The Prisoner's Dilemma is a classic concept in game theory that explores the tension between cooperation and self-interest. It is often used as an experimental tool in social psychology to study decision-making, trust, and cooperation.

In the standard version of the Prisoner's Dilemma, two individuals are arrested for a crime and are held in separate cells. They are both given the opportunity to cooperate with each other or betray each other by confessing to the crime. The outcomes are as follows:

1. If both prisoners remain silent (cooperate), they each receive a moderate sentence for a lesser charge.
2. If one prisoner confesses (betrays) and the other remains silent, the betrayer receives a minimal sentence, while the other prisoner receives a severe sentence.
3. If both prisoners confess (betray), they both receive a moderately severe sentence.

The dilemma arises because each prisoner must decide whether to trust the other person and cooperate for a potentially better outcome for both or act in their self-interest by betraying the other, which might lead to a better personal outcome if the other remains silent.

### Special thanks

This tutorial was developed by James Houghton, Mohammad Alsobay, and Michael Li, with support from Millie Gu and others.
