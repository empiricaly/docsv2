# Setup

1. Run the installation script:

```
curl https://install.empirica.dev | sh
```

That's it, you're done! Proceed to create your experiment:

{% content-ref url="../quick-start.md" %}
[quick-start.md](../quick-start.md)
{% endcontent-ref %}

### Pre-release cleanup

If have installed `empirica` before the official launch (before January 2023), you might need to clean the beta version from your system.

On macOS:

```
rm -rf $HOME/.local/share/empirica
rm -rf "$HOME/Library/Application Support"
```

On Linux:

```
rm -rf $HOME/.local/share/empirica
```

Then, proceed to reinstall empirica with the command at the top of this page.

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
