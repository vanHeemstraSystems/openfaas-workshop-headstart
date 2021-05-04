# 200 - OpenFaaS CLI

You can install the OpenFaaS CLI using the official bash script, brew is also available but can lag one or two versions behind.

With MacOS or Linux run the following in a Terminal:

```$ curl -sLSf https://cli.openfaas.com | sudo sh```

For Windows, run this in Git Bash:

```$ curl -sLSf https://cli.openfaas.com | sh```

***Note***: If you run into any issues then you can download the latest ```faas-cli.exe``` manually from the [releases page](https://github.com/openfaas/faas-cli/releases). You can place it in a local directory or in the ```C:\Windows\``` path so that it's available from a command prompt.

We will use the ```faas-cli``` to scaffold new functions, build, deploy and invoke functions. You can find out commands available for the cli with ```faas-cli --help```.

Test the ```faas-cli```. Open a Terminal or Git Bash window and type in:

```
$ faas-cli help
$ faas-cli version
```
