## Parcel `process` issues

1. `pnpm install`
2. `pnpm run parcel`

See:

```bash
🚨 Build failed.

@parcel/core: Failed to resolve 'buffer' from
'./node_modules/.pnpm/axios@1.2.1/node_modules/axios/lib/helpers/toFormData.js'
```

3. A temp fix, to package.json, add:

```json
"alias": {
  "process": {
    "global": {}
  }
},
```

Now we see:

```bash
🚨 Build failed.

@parcel/core: Failed to resolve 'process' from
'./node_modules/.pnpm/@sentry+utils@7.28.0/node_modules/@sentry/utils/esm/node.js'
```


Tested with node v16.13.1 and 18.12.1
