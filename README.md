
For VS Code, the following lines need to be in `.vscode/settings.json` to enable the new Typescript compiler written in Go:

```json
{
  "js/ts.experimental.useTsgo": true,
  "js/ts.tsdk.path": "./node_modules/typescript"
}
```

For compatibility with Eslint, in `package.json` install the following dependencies:

```json
  "devDependencies": {
    "typescript": "npm:@typescript/typescript6@^6.0.2",
    "@typescript/native": "npm:typescript@^7.0.2",
    "typescript-eslint": "^8.71.1"
  }
```

In `eslint.config.mjs`, import `globals` and enable them in `languageOptions`:

```json
import globals from 'globals';

{
  languageOptions: {
      globals: {
        ...globals.node,
      },
  },
}
```
