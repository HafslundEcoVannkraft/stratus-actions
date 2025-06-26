# Hello World Composite Action

A simple GitHub composite action that prints a hello world message. This action is part of our monorepo collection of reusable GitHub Actions.

## Features

- 🚀 Lightweight and fast execution
- 🔧 Simple bash script implementation
- 📦 Easy to integrate into existing workflows
- 🎯 Perfect for testing and learning GitHub Actions

## Usage

```yaml
name: Hello World Workflow

on:
  push:
    branches:
      - main
  workflow_dispatch:

jobs:
  hello:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Say Hello
        uses: HafslundEcoVannkraft/stratus-actions/hello-world@v1
```

## Location in Monorepo

```
repository-root/
├── hello-world/              # This action
│   ├── README.md
│   ├── action.yml
│   └── entrypoint.sh
├── release/                  # Release action
├── build-scope-analyzer/     # Build scope analyzer action
└── other-actions/            # Other composite actions
```

## File Permissions

Make sure the entrypoint script has executable permissions:

```bash
git update-index --chmod=+x hello-world/entrypoint.sh
```

## Inputs

This action doesn't require any inputs.

## Outputs

This action doesn't produce any outputs. It simply prints "Hello world from stratus-actions composite action" to the workflow logs.

## Examples

### Basic Usage

```yaml
- name: Say Hello
  uses: HafslundEcoVannkraft/stratus-actions/hello-world@v1
```

### Using Specific Version

Use the v1 tag for the first production release after a full history reset:

```yaml
- uses: HafslundEcoVannkraft/stratus-actions/hello-world@v1
```

---

# Hello World (Composite) Action

A minimal composite action that echoes a greeting and demonstrates inputs/outputs.

## Usage

```yaml
- name: Hello World (Composite)
  uses: ./hello-world
  with:
    who-to-greet: "Stratus"
```

## Inputs

- `who-to-greet`: Who to greet (default: `World`)

## Outputs

- `time`: The time the greeting was generated

---

## When to use Composite Actions

- For simple logic, shell steps, or combining other actions. Fast, no build required.
- Use Docker actions for custom environments or dependencies.

## License

MIT
