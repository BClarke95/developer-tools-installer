# IBM Developer Tools
These scripts perform an installation of the IBM Developer Tools CLI environment. The IDT is a plugin to the IBM Bluemix CLI. Our general target environment is the IBM Cloud, including public, dedicated, and local hybrid.


[![](https://img.shields.io/badge/bluemix-powered-blue.svg)](https://bluemix.net)
![Platform](https://img.shields.io/badge/platform-BASH-lightgrey.svg?style=flat)
![Platform](https://img.shields.io/badge/platform-PowerShell-lightgrey.svg?style=flat)


The following are platform specific concerns and notes you should be aware of.

## MacOS &amp; Linux Installation

The following command can install the IBM Developer tools in a single invocation.  Open up a terminal and run the following command:

```
curl -sL https://ibm.biz/idt-installer | bash
```

By default, this installer will use the 'brew' installer on MacOS, if available. If you explicitly do not want to use brew, execute the following command with `--nobrew` option:

```
curl -sL https://ibm.biz/idt-installer | bash -s -- --nobrew
```

Once complete, there will be three aliases defined to access the IDT:
- `idt` : Main command line tool for IBM cloud native development (shortcut to 'bx dev')
- `idt-update` : Update your IDT environment to the latest versions
- `idt-uninstall` : Uninstall the IBM Developer Tools

Access the [platform-specific readme](./linux-installer/README.md) for additional details.

This script has only been tested on Ubuntu Linux systems, although it should behave properly on other distros. If you run into any issues, please let us know on [Slack](https://ibm.biz/IBMCloudNativeSlack) or file an issue on our [GitHub repo](https://github.com/ibm-cloud-tools/idt-installer).



## Windows Installation
To install the IBM Developer Tools CLI on Windows 10 or newer:

1. Open Windows PowerShell by right-clicking and select "Run as Administrator".
2. Run this command:
```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```

Access the [Windows-specific readme](./windows-installer/README.md) for additional details.



## Feedback

We can be reached on [Slack](https://ibm.biz/IBMCloudNativeSlack) or file an issue on our [GitHub repo](https://github.com/ibm-cloud-tools/idt-installer).


## Internal IBM users

IBM user can utilize this installer pulling the Bluemix cLI and plugins from pre-release internal servers. In order to have the installer utilize internal servers, set the following environment variables (eg in `~/.bashrc`), using the proper actual values:

```
export IDT_INSTALL_BMX_URL="https://clis.<internal_bluemix_staging_url>/install"
export IDT_INSTALL_BMX_REPO_NAME="stage"
export IDT_INSTALL_BMX_REPO_URL="https://plugins.<internal_bluemix_staging_url>"
```

If you need assistance on the proper values, just ask in any of the internal slack channels.