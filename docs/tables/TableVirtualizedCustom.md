TableVirtualizedCustom
-----

`TableVirtualizedCustom` is a wrapper around the `TableVirtualized`. It provides simple interfaces for customizing columns.

### Prop Types

| Property | Type | Required? | Default | Description |
|:---|:---|:---:|:---|:---|
| bodyRowCount | number | ✓ | | |
| bodyRowHeight | number| | 40 | |
| children | [Column](Column.md) | | | |
| data | [object] | | | |
| emptyMessage | string| | | Messages to show when there's no data. |
| isEmptyGhost | bool | | false | Display a empty table in the background. |
| isLoading | bool | | false | Display a loading icon if true. |
