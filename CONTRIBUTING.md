# Contributing an automation

Open a pull request that adds or changes a file under `automations/`.

**What you publish is public and permanent.** Closing a pull request or deleting a file does not remove copies. Check your text for internal hostnames, repository and application names, account IDs, people's names and secrets. Use a `{{parameter}}` for anything specific to your organisation.

## File format

```yaml
apiVersion: automation.opsmx.io/v1
kind: Automation
name: License report
description: Lists the components of an image whose licenses need attention.
functions: [License compliance]
personas: [Security engineer]
requests:
  - List the components of the image {{image}} with their licenses.
```

| Field | Rule |
|---|---|
| `apiVersion`, `kind` | exactly as above |
| `name` | 3 to 60 characters, no space at either end |
| `description` | required, at most 500 characters; say what the requests actually do |
| `functions`, `personas` | optional, at most 10 each, each at most 40 characters |
| `requests` | 1 to 20, run in order; each at most 2,000 characters, 20,000 in total |
| parameters | `{{name}}` in a request: letters, digits and underscores, not starting with a digit; at most 10 |

An instance skips a file that breaks a rule.

## Path rules

- The path below `automations/`, without `.yaml`, with `/` written as `.`, is the automation's identity.
- Folder and file names must not contain dots or spaces.
- Use a folder for you or your organisation, for example `automations/com/example/...`. Do not change another publisher's files without their agreement.
- **Do not move or rename a published file.** That creates a new automation, and existing installs of the old one are marked withdrawn.

Any change to a file is a new version. People who installed it see the difference and choose whether to update.

## Writing requests

- Say plainly what each request does. If a request changes anything (raises a pull request, starts a scan, sends data somewhere), say so in the description.
- Do not ask for data to be sent outside the user's SSD instance without making it obvious in the name and description.
