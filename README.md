Rust Darwin Builder Action
========================

GitHub action for building Darwin targeted rust binaries (x86_64-apple-darwin). 

```yaml
- uses: actions/cache@v2
  with:
    path: |
      ~/.cargo/registry
      ~/.cargo/git
      target
    key: darwin-cross-cargo-${{ hashFiles('**/Cargo.lock') }}
- uses: aig787/rust-darwin-cross-builder@v1.0
  with:
    args: build --release --all-features
    credentials: ${{ secrets.GIT_CREDENTIALS }}
```

### Inputs
| Variable | Description | Required | Default |
|----------|-------------|----------|---------|
| args     | Arguments passed to cargo | true | `build --release` | 
| credentials | If provided git will be configured to use these credentials and https | false | |
| directory | Relative path under $GITHUB_WORKSPACE where Cargo project is located | false | |

### Credits:
* [osxcross](https://github.com/tpoechtrager/osxcross)
* [osxcross-extras](https://github.com/liushuyu/osxcross-extras)
