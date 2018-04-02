Column
-----

`Column` is just a convenient way to specify renderers and other information for a column.

### Prop Types

| Property | Type | Required? | Default | Description |
|:---|:---|:---:|:---|:---|
| cell | func | | | Function to render a cell. [learn more](#cellrenderers)|
| children | func | | | Function to render a cell. It's the same as `cell`. [learn more](#cellrenderers)|
| columnKey | number or string | ✓ | | The name of property of the data object. |
| flexGrow | number | | 1 | Like `flex-grow`|
| flexShrink | number | | 1 | Like `flex-shrink`|
| header | func | | | Function to render a header cell. [learn more](#headerrenderers)|

### cellRenderers

Renderers render a body cell. It should looks like:

```javascript
function({
  cellData, // The data for this specific cell, if any.
  columnIndex, // Horizontal (column) index of cell
  isScrolling, // The Grid is currently being scrolled
  isVisible, // This cell is visible within the grid (eg it is not an overscanned cell)
  key, // Unique key within array of cells
  parent, // Reference to the parent Grid (instance)
  rowData, // The data for the row
  rowIndex, // Vertical (row) index of cell
  style // Style object to be applied to cell (to position it);
        // This must be passed through to the rendered cell element.
}) {
  return (
    <div key={key} style={style} >
      {content}
    </div>
  )
}
```

### headerRenderers

Renderers render a header cell. The function accepts the following named parameters:

```javascript
function({
  columnIndex, // Horizontal (column) index of cell
  columnKey,
  isScrolling, // The Grid is currently being scrolled
  isVisible, // This cell is visible within the grid (eg it is not an overscanned cell)
  key, // Unique key within array of cells
  parent, // Reference to the parent Grid (instance)
  rowData, // The data for the row
  rowIndex, // Vertical (row) index of cell
  style // Style object to be applied to cell (to position it);
        // This must be passed through to the rendered cell element.
}) {
  return (
    <div key={key} style={style} >
      {content}
    </div>
  )
}
```
