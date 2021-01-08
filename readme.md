This repo demonstrates an issue running `vercel dev` if the `build` command runs a process that doesn't finish.

If the `build` script in `package.json` is finite, everything works fine:

```json
{
  "scripts": {
    "start": "vercel dev",
    "build": "snowpack build"
  }
}
```

However, if it launches a process for watching changes, for example, Vercel's dev build doesn't run (although, in this case, the Snowpack build does complete):

```json
{
  "scripts": {
    "start": "vercel dev",
    "build": "snowpack build --watch"
  }
}
```
