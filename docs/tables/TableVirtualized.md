TableVirtualized
--------

A base table based on [React Virtualized Grid](https://github.com/bvaughn/react-virtualized/blob/master/docs/Grid.md).

The table consists of four parts.
 <table>
   <tbody>
    <tr><td>NameHeader</td><td>DataHeader</td></tr>
    <tr><td>NameBody</td><td>DataBody</td></tr>
   </tbody>
 </table>


### Prop Types
| Property | Type | Required? | Default | Description |
|:---|:---|:---:|:---|:---|
| bodyRowCount | number | ✓ | | Number of rows in the body grids (NameBody & DataBody).|
| bodyRowHeight | number | | 40 | Height of each body row.|
| dataColumnCount | number | ✓ | | Number of columns in the data grids (DataHeader & DataBody)|
| dataColumnWidth | number or [number]| | ✓ | Width of each body column. If a number, it'll be applied for all columns; if an array of number, it must be equal to the `dataColumnCount`. The actual value is calculated with scaleColumnWidthMode. |
| growFactors | number or [number] | | 1 | Kind of like the flex-grow for flexbox. If a number, it'll be applied for all columns; if an array of number, it must have the same length as the `dataColumnWidth`.|
| headerRowHeight | number | | 40 | Height of the header row.|
| id | string | | TableVirtualized | The id of the root element.|
| indicatorBodyChange | any | | | [learn more](#indicators) |
| indicatorHeaderChange | any | | | [learn more](#indicators) |
| indicatorTableChange | any | | | [learn more](#indicators) |
| minVisibleRowCount | number | | 2 | |
| nameColumnWidth | number | | 200 | Width of the name column. |
| overscanColumnCount | number | | 0 | |
| overscanRowCount | number | | 5 | |
| renderDataBodyCell | function | | | Responsible for rendering a cell of DataBody given an row and column index. [learn more](#renderers)|
| renderDataHeaderCell | function | | | Responsible for rendering a cell of DataHeader given an row and column index. [learn more](#renderers)|
| renderNameBodyCell | function | | | Responsible for rendering a cell of NameBody given an row and column index. [learn more](#renderers)|
| renderNameHeaderCell | function | | | Responsible for rendering a cell of NameBody given an row and column index. [learn more](#renderers)|
| scaleColumnWidthMode | string | | AUTO | Specify how to calculate the column widths. |
| shrinkFactors | number or [number] | | 1 | Kind of like the flex-shrink for flexbox. If a number, it'll be applied for all columns; if an array of number, it must have the same length as the `dataColumnWidth`. |

### Indicators

The React Virtualized Grid component is PureComponent and doesn't have access to the data directly. All data access are through those render functions. So it's necessary to pass indicators for data change.

### Renderers

The React Virtualized Grid component needs a renderer function to render each cell.

A render looks like this.
```javascript
function cellRenderer ({
  columnIndex, // Horizontal (column) index of cell
  isScrolling, // The Grid is currently being scrolled
  isVisible,   // This cell is visible within the grid (eg it is not an overscanned cell)
  key,         // Unique key within array of cells
  parent,      // Reference to the parent Grid (instance)
  rowIndex,    // Vertical (row) index of cell
  style        // Style object to be applied to cell (to position it);
               // This must be passed through to the rendered cell element.
}) {
}
```
