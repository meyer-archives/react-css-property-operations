# react-css-property-operations

The project is a `webpack`-bundled version of `react-dom/lib/CSSPropertyOperations.js` for use outside of React.

## Installation

Install [`react-css-property-operations`][npm] with `yarn` or `npm`:
- `yarn add react-css-property-operations`
- `npm install react-css-property-operations`

## Updating

The update tasks are all bundled together in a single `rake` task.
Running `rake` from the command line in the root of this project will do the following:

1. Upgrade `react` and `react-dom` to the latest versions.
2. Update the version number in `package.json` to match `react-dom`’s version number.
3. Rebuild `./lib/CSSPropertyOperations.js`.

[npm]: https://www.npmjs.com/package/react-css-property-operations
