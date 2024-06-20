# Setup

1. Run the installation script:

```sh
curl -fsS https://install.empirica.dev | sh
```

That's it, you're done! Proceed to create your experiment:

{% content-ref url="../quick-start.md" %}
[quick-start.md](../quick-start.md)
{% endcontent-ref %}

{% hint style="info" %}
#### Running an older version?

If you are running on an older version and are encountering version issues, try running the curl command above again. It should reset your local install.
{% endhint %}

{% hint style="success" %}
#### Upgrading

To upgrade the empirica command globally on your machine, you can either run `empirica upgrade --global` outside of any projects, or run the curl command above again.
{% endhint %}

{% hint style="warning" %}
#### Volta error

Some users have been seeing a Volta error that prevents empirica from properly managing node (here: [https://github.com/volta-cli/volta/issues/1744](https://github.com/volta-cli/volta/issues/1744)). It can be resolved it by installing the right versions of node manually and removing the `volta` lines from `client/package.json` and `server/package.json`.
{% endhint %}

### **A note about Windows Setup**

{% hint style="warning" %}
Windows is currently not natively supported. Empirica does work on Windows with Microsoft's WSL 2.
{% endhint %}

{% hint style="danger" %}
The installation of WSL 2 has been greatly simplified since Windows 10 version 2004, released at the end of 2021. Windows 11 also benefits from the new much simplified procedure. The following documentation does not cover the new installation. If you are using Windows 10 2004 and higher, we recommend you look online how to install WSL 2, then you can follow the macOS/Linux procedure above.
{% endhint %}

Empirica is built on industry-standard open-source web technologies which run best in Unix-like operating systems such as Linux and macOS. \*\*\*\*

_If you are a Windows user and get stuck at any point in the development process, please contact joshua.becker@ucl.ac.uk or join the_ [_Slack channel_](https://join.slack.com/t/empirica-ly/shared\_invite/zt-1fb34yq47-YlgYUJmXJAdv7QmHsa\_fdw) _for community-based technical support on a wide range of topics._

{% content-ref url="windows-instructions.md" %}
[windows-instructions.md](windows-instructions.md)
{% endcontent-ref %}
