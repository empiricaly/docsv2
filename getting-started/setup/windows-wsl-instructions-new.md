---
description: Updated version of WSL?
---

# Windows WSL Instructions (new)

If you have not already done so, **install** [**Windows Subsystem for Linux (WLS)**](https://learn.microsoft.com/en-us/windows/wsl/) by opening your terminal and running:

```
wsl --install
```

Now you may be prompted to create a username and password. Make sure to write down your login credentials for the future!

Note: Copying and pasting may be disabled in the default settings of your WLS terminal. To remedy this, right-click the title bar and select 'Properties --> Options --> Use Ctrl+Shift+C/V as Copy/Paste.'

**Install Empirica** in your WSL terminal with the following command. You may be prompted to use the WSL password you just created.

```sh
curl https://install.empirica.dev | sh
```

🎉 Congrats, you've now installed Empirica! 🎉
