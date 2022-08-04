The issue with `instanceof` only occurs when using Svelte Headless Table plugins.

To visualize the issue, follow the instructions:

Go to `node_modules/svelte-headless-table/plugins/addSortBy.js`

After line 131, add the following:

```
console.log('toggling');
console.log(cell);
console.log(DataHeaderCell);
console.log(cell instanceof DataHeaderCell);
```

With `yarn dev`, cell instanceof DataHeaderCell returns false.
With `yarn build && yarn preview`, cell instanceof DataHeaderCEll returns true.
