createTableWidthManager
-----

The `createTableWidthManager` returns a `table width manager` which help micmic the behavior of flexbox. By default, React Virtualized cells do not support flexbox because each cells are separated. There's no parent container for cells in a row or a column. Width and height for a cell is calculated given it's position in the grid and the size of the Grid.

### Parameters
| Name | Type | Required  | Default | Description
| --- | --- | --- | --- | --- |
| widths | number or [number] | ✓ | | Width of each column. If a number, it's applied for each column. [learn more](#Widths)|
| columnCount | number | ✓ | | Number of columns. |
| growFactors | number or [number] | ✓ | | Like flex-grow. [learn more](growFactors & shrinkFactors)|
| shrinkFactors | number or [number] | ✓ | | Like flex-shrink. [learn more](growFactors & shrinkFactors)|
| mode | string | ✓| | Specify how column widths are calculated. |
| tableWidth | number| | 0 | Width of the table. |

### Widths

The `widths` acts as the base width for columns. It is affected by the `mode`.

### growFactors & shrinkFactors

The `growFactors` and `shrinkFactors` work almost exactly as the `flex-grow` and `flex-shrink`.

When there're extra space available. The column width is calculated by

`baseWidth + extractLength x growFactor / sum(growFactors)`.

When the columns need to shrink. The column width is calculated by:

`baseWidth - totalLengthToShrink x (baseWidth x growFactor) / (sum(baseWidth1 x growFactor1 + baseWidth2 x growFactor2 + ...))`

### mode
