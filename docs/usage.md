# Usage

## Setup
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
        uses: actions/checkout@v4

      - name: 📦 Create draft release from milestone
        uses: quaternionmedia/milestones@v1
        with:
          # Save release as a draft (default: true)
          draft: false # Setting this will publish the release immediately
```

## Create milestone
Create a new GitHub milestone, where the first word is the version tag name for the release you will be publishing.

For example: `v0.1.0 Test 🧪` -> `v0.1.0`

!!! abstract "Naming conventions"

    The milestone name can contain emojis and other markdown characters, but the tag name must only contain alphanumeric symbols.

## Close milestone
Close the milestone, and the action will run. Once complete, check the "Releases" section of your repository. There should be a new draft at the top of the page with the name of the milestone. 

If everything looks good, you can publish the release by clicking the "Publish release" button, and it will be visible on the releases page and available for download!
