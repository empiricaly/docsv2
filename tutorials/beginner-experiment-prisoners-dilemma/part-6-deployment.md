# Part 6: Deployment

🎉 Congratulations 🎉, you've finished building your first experiment with Empirica! Now you need to deploy it to a server, so that you can send participants to it.&#x20;

There are a number of ways to do this, including setting up your own servers on Amazon Web Services, DigitalOcean, or a similar platform.

The Emprica team is also working on a streamlined way to deploy experiments, with a command built into empirica. This is currently an "alpha" version designed to test feasibility, and so is likely to change quite significantly in the coming months:

```
empirica cloud deploy
```

This will take care of bundling the code for production, and managing servers. It will return a link that you can direct participants to, and interact with through the admin interface to set up batches. Stay tuned for more details!
