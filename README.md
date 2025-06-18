# Milestones

Github action to create draft releases from closed milestones.

## Marketplace

Available on GitHub marketplace: [draft-release](https://github.com/marketplace/actions/draft-release)

## Documentation

[quaternionmedia.github.io/milestones](https://quaternionmedia.github.io/milestones/)

## Example

To use this action, simple place the following file in your `.github/workflows/` folder.

```yml title=".github/workflows/draft-release.yml"
name: 📝 Draft Release
on:
  milestone:
    types: [closed]
jobs:
  release:
    name: ✏️ Create draft release
    runs-on: ubuntu-latest
    steps:
      - name: 📰 Checkout
        uses: actions/checkout@v4

      - name: 📦 Create release from milestone
        uses: quaternionmedia/milestones@v1
        with:
          # Save release as a draft (default: true)
          draft: false # Setting this will publish the release immediately
```

## Credits

[Quaternion Media, LLC](https://quaternion.media)
