# README

- Subject [knip issue-678](https://github.com/webpro-nl/knip/issues/678)
- the deep file structure should simulate a project path, which contains `builds`


## Reproducer

The repository presents a correct JS repository, which uses the dependency `chalk`.

```bash
cd knipuser/cicd/builds/project42
npm ci
npm run knip

# > project42@1.0.0 knip
# > knip

# Unused devDependencies (1)
# chalk  package.json
```

The result is wrong. `chalk` is used. See analysis [in the issue](https://github.com/webpro-nl/knip/issues/678).

Check `npm run knip -- --debug` to see that `src/index.mjs` is not matching, although entrypoint and it exists.