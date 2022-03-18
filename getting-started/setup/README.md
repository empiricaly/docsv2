# Setup

{% hint style="danger" %}
**Only macOS** is supported at this point. We will release Windows and Linux version in the near future.
{% endhint %}

1. Install Node.js via [https://nodejs.org/en/](https://nodejs.org/en/) (download and install the LTS bundle on the left)&#x20;
2.  Run the installation script:

    ```
    curl https://get.empirica.dev | sh
    ```

That's it, you're done!  Proceed to creating your experiment:

{% content-ref url="../quick-start.md" %}
[quick-start.md](../quick-start.md)
{% endcontent-ref %}

### **A note about Windows 10 Setup**

{% hint style="warning" %}
Windows is currently not supported.
{% endhint %}

Empirica is build on industry-standard open-source web technologies which run best in Unix-like operating systems such as Linux and MacOS.  ****&#x20;

Running Meteor apps on Windows can be unreliable, as apps struggle to install and launch. Whilst stopping and trying again multiple times (as well as making sure there are no processes that slow down the installation of the Meteor files) might work, it is not recommended.

In order to run Empirica reliably in Windows, you will need to enable developer settings within advanced Windows settings and download/install the new version of Windows Subsystem for Linux (WLS2).&#x20;

_If you are a Windows user and get stuck at any point in the development process, please contact joshua.becker@ucl.ac.uk or join the Slack channel for community-based technical support on a wide range of topics._

{% content-ref url="windows-instructions.md" %}
[windows-instructions.md](windows-instructions.md)
{% endcontent-ref %}
