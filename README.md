# Script to track % of typescript in your repo / project

If you are migrating to TypeScript it may be nice to keep track of how you are doing for a particular project, here is an example of using `Tokei` and `jq` to do this.

- Tokei https://github.com/XAMPPRocky/tokei
- Jq https://github.com/stedolan/jq

You can install both via *brew*
- `brew install jq`
-`brew install tokei`

Run this in the root of your project.

Use `-e` to exlude any tests, fixtures you don't want to count
```
tokei
-e test/fixtures
-o json | jq '100 * .inner.TypeScript.code / (.inner.JavaScript.code + .inner.TypeScript.code)'
```

![](https://github.com/lili2311/script-typescript-percent/blob/master/Screen%20Shot%202020-02-16%20at%2018.59.21.png?raw=true)
