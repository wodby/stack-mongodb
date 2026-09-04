# MongoDB application stack for Kubernetes on Wodby

Deploy MongoDB applications on Kubernetes with Wodby, with an optional
browser-based Mongoku administration interface.

This repository defines the Wodby stack manifest and default service
composition for MongoDB.

- [MongoDB stack on Wodby](https://wodby.com/stacks/mongodb)
- [Browse Wodby application stacks](https://wodby.com/stacks)
- [Wodby stack documentation](https://wodby.com/docs/2.0/stacks/)
- [Stack manifest reference](https://wodby.com/docs/2.0/stacks/template/)

## Service definition

- [MongoDB service on Wodby](https://wodby.com/services/mongodb)
- [Mongoku service on Wodby](https://wodby.com/services/mongoku)

## What's included

| Component / service | Default configuration |
| --- | --- |
| MongoDB<br>`mongodb` | optional; enabled by default; volumes: `data` 10 GB |
| Mongoku<br>`mongoku` | optional; disabled by default; link: `db` → `mongodb` |

Enabled optional services are selected by default but can be excluded when an
app is created. Required services cannot be excluded.

## Deploy this stack

Add this stack from the Wodby catalog, then configure its enabled services and
integrations.

Review service versions, storage, and integrations when creating the
application. The same stack can be reused across development, staging, and
production environments.

## Maintain a custom version

1. Fork this repository.
2. Edit the stack manifest.
3. Import the repository as a [Git-backed stack](https://wodby.com/docs/2.0/stacks/create/#create-a-git-backed-stack).

When replacing or renaming a stack service, update every related link target
and derivative reference. Stack-local names and referenced service names are
distinct identifiers.

Validate the manifest with:

```bash
wodby stack validate-manifest stack.yml --org <org-id>
```

See the [stack manifest reference](https://wodby.com/docs/2.0/stacks/template/) and the [managed services index](https://github.com/wodby/services).
