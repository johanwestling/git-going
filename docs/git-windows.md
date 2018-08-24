# Install git in Windows

[Back to README](../README.md)

1. Enable *Windows Subsystem for Linux* (WSL)
    1. Press **WIN + Q**
    1. Enter **powershell**
    1. Press **CTRL + SHIFT + ENTER**
    1. Click **Yes** on the following prompt
    1. Enable WSL:
        ```
        Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
        ```
1. Install Bash on Ubuntu on Windows (BUW)
    1. Press **WIN + Q**
    1. Enter **cmd**
    1. Press **CTRL + SHIFT + ENTER**
    1. Click **Yes** on the following prompt
    1. Install BUW:
        ```
        lxrun /install /y
        ```
1. Launch BUW
    1. Press **WIN + Q**
    1. Enter **bash**

[Back to README](../README.md)
