# Software built by Dmitry Kotik

## How to renew a Github token

To use GoReleaser with GitHub, you must provide a GitHub token to allow it to create releases,
upload artifacts, and tag your repository. GoReleaser automatically looks for an environment
variable named `GITHUB_TOKEN`.

Use Fine-grained Personal Access Token with access to:

- List of repositories that the token can modify, same as those in casks folder here.
- **Read** and **Write** access to repository Contents.

Make sure the token name matches the workflow environment:

```yaml
      - name: Run GoReleaser
        uses: goreleaser/goreleaser-action@v7
        with:
          distribution: goreleaser
          version: latest
          args: release --clean
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }} 
```
