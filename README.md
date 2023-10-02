# [WIP] Prowlarr-Indexers
Prowlarr Indexers used by Cardigann


The indexer can be validated using the schema from Cardigann.

```js
ajv test -d ".\Custom\torrentio.yml" -s ".\v9-schema.json" --valid --all-errors -c ajv-formats --spec=draft2019
```

Note that the following npm packages are required `ajv-cli-servarr ajv-formats` These can be installed globally on your system with `npm install -g ajv-cli-servarr ajv-formats`

# Coming soon..