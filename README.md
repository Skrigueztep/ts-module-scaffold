# TS Module Scaffold

## Changes or modifications according your porpuse

### General changes

`package.json`

```
{
    ...
    "name": "<my-module-name>"
    ...
}
```

`tsconfig.json`

```
{
    ...
    "outDir": "./dist/<my-module-name>",
    ...
}
```

### CLI

`package.json`

This help you to exec your nodejs project like CLI
```
{
    ...
    "bin":  {
        "<my-cli-name>" : "<my-compiled-index-js-file>.js"
    }
    ...
}
```
`index.ts`

This help you to exec your entry file without runtime declaration
```
#!/usr/bin/env node
```

### Native module

`package.json`

```
{
    ...
    "main": "<my-compiled-index-js-file>.js",
    // or use code as shown below in NodeJS v14+ or v16+
    "exports": {
        ".": <my-compiled-index-js-file>.js"
    }
    ...
}
```

If you need to expose code by consuming it from a project or to be able to public and you need
know that things your module expose, conventionally for JS modules it had a `.d.ts` file for types
declarations but now on TS, you can generate it vía typescript compiler enabling this config:

`tsconfig.json`

```
{
    ...
    "declaration": true,
    "declarationDir": "./dist/<my-module-name>/types",
    ...
}
```

And enabling these vía package.json

`package.json`

```
{
    ...
    "types": "<my-compiled-index-js-file>/types",
    ...
}
```

### Assets exposition

`package.json`

```
{
    ...
    "exports": {
        ".": <my-compiled-index-js-file>.js",
        "./myStylesheet.css": <my-compiled-directory>/myStylesheet.css",
        "./myJsonFile.json": <my-compiled-directory>/myJsonFile.json",
        "./myImage.svg": <my-compiled-directory>/someLogoimage.svg"
    }
    ...
}
```
