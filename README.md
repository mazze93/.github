# .github

Default community health files for [@mazze93](https://github.com/mazze93) repositories.

GitHub applies these to any account-owned repo that does not define its own file of the same type. They do not appear in each repo’s tree or clone.

## Files

- [SECURITY.md](SECURITY.md) — account-wide security policy: vulnerability disclosure, CVD timeline, safe harbor.
- [`.github/PULL_REQUEST_TEMPLATE/artifact.md`](.github/PULL_REQUEST_TEMPLATE/artifact.md) — choosable PR template for documentation / advisory / method artifacts (provenance, grounding, presentation readiness).

## Using the artifact PR template

Repos without their own pull-request templates inherit this one. Pick it explicitly when opening a PR:

**Web**

```text
https://github.com/mazze93/<repo>/compare/<base>...<head>?quick_pull=1&template=artifact.md
```

**gh**

```bash
gh pr create --draft \
  --title "docs: …" \
  --body-file "$(gh api repos/mazze93/.github/contents/.github/PULL_REQUEST_TEMPLATE/artifact.md --jq '.content' | base64 -d)"
```

Or paste from the template file after cloning this repo (`meta/dot-github`).

A repository that adds its own `.github/PULL_REQUEST_TEMPLATE/` or `pull_request_template.md` overrides these defaults for that repo only.
