# Setup

1. Run the installation script:

```
curl https://get.empirica.dev | sh
```

That's it, you're done!  Proceed to create your experiment:

{% content-ref url="../quick-start.md" %}
[quick-start.md](../quick-start.md)
{% endcontent-ref %}

### **A note about Windows Setup**

{% hint style="warning" %}
Windows is currently not natively supported. Empirica does work on Windows with Microsoft's WSL 2.
{% endhint %}

{% hint style="danger" %}
The installation of WSL 2 has been greatly simplified since Windows 10 version 2004, released at the end of 2021. Windows 11 also benefits from the new much simplified procedure. The following documentation does not cover the new installation. If you are using Windows 10 2004 and higher, we recommend you look online how to install WSL 2, then you can follow the macOS/Linux procedure above.
{% endhint %}

Empirica is built on industry-standard open-source web technologies which run best in Unix-like operating systems such as Linux and macOS.  ****&#x20;

Running Meteor apps on Windows can be unreliable, as apps struggle to install and launch. Whilst stopping and trying again multiple times (as well as making sure there are no processes that slow down the installation of the Meteor files) might work, it is not recommended.

In order to run Empirica reliably in Windows, you will need to enable developer settings within advanced Windows settings and download/install the new version of Windows Subsystem for Linux (WLS2).&#x20;

_If you are a Windows user and get stuck at any point in the development process, please contact joshua.becker@ucl.ac.uk or join the Slack channel for community-based technical support on a wide range of topics._

{% content-ref url="windows-instructions.md" %}
[windows-instructions.md](windows-instructions.md)
{% endcontent-ref %}
