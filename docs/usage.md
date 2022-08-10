# Usage

To use this action, simple place the following file in your `.github/workflows/` folder.

```yml title=".github/workflows/draft-release.yml"
name: 📦 Release
on:
  milestone:
    types: [closed]
jobs:
  release:
    name: 📝 Draft Release
    runs-on: ubuntu-latest
    steps:
      - name: 📰 Checkout
        uses: actions/checkout@v3

      - name: 📦 Create draft release from milestone
        uses: quaternionmedia/milestones@main
```
