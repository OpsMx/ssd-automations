# SSD Automations

A public collection of automations for [OpsMx SSD](https://www.opsmx.com/). An automation is a saved list of plain-language requests that SSD's chat carries out in order.

Installing from SSD (the **Marketplace** tab) is being built and is not available yet.

## Before you use one

- Anyone can propose an automation. A maintainer reviews each pull request, but nothing else checks what it does.
- An automation runs **with your access** in your SSD instance. Read its requests before you install or update it.

## Layout

One YAML file per automation under `automations/`. The file's path is the automation's identity:

```
automations/com/opsmx/security/repositoryScanReport.yaml  ->  com.opsmx.security.repositoryScanReport
```

To add or change one, see [CONTRIBUTING.md](CONTRIBUTING.md).
