# dependabot-auto-merge


⚠️ **Warning** ⚠️ This project is not intended for use outside of Contentful and as such it is not supported by Contentful.



## Usage

To reference the action, create a workflow in your project in `.github/workflows/` e.g.

`.github/workflows/dependabot-approve-and-request-merge.yml`:

```yaml
name: "dependabot approve-and-request-merge"

on:
  pull_request_target

jobs:
  worker:
    runs-on: ubuntu-latest

    if: github.actor == 'dependabot[bot]'
    steps:
      - uses: contentful/dependabot-auto-merge@v1
        with:
          github_token: ${{ secrets.GITHUB_TOKEN_WITH_WRITE_ACCESS }}
```

You will need to ensure that `GITHUB_TOKEN_WITH_WRITE_ACCESS` belongs to a user which has write access to the repository.
