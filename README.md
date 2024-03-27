### Project Overview <a name="project-overview"></a>
This project aims to provide a command-line tool for manipulating tables and cells within them. The tool allows users to perform various operations such as modifying table structure, setting cell content, calculating sums and averages, and working with temporary variables.
The project consists of a command-line tool called `sps`, which stands for "Spreadsheet Processor." It operates on text files representing tables and executes commands specified by the user to manipulate the table structure and content.

### Command Syntax <a name="command-syntax"></a>
The syntax for executing the `sps` tool is as follows:

```
./sps [-d DELIM] CMD_SEQUENCE FILE
```
- `-d DELIM`: Optional flag to specify the delimiter used in the input file.
- `CMD_SEQUENCE`: Sequence of commands to be executed on the table.
- `FILE`: Path to the input file containing the table data.

### Command Reference <a name="command-reference"></a>

#### Selection Modification Commands <a name="selection-modification-commands"></a>
Commands for modifying the selection of cells within the table:

- `[R,C]`: Selects the cell at row `R` and column `C`.
- `[R,_]`: Selects the entire row `R`.
- `[_,C]`: Selects the entire column `C`.
- `[R1,C1,R2,C2]`: Selects a window of cells from row `R1` to `R2` and column `C1` to `C2`.
- `[_,_]`: Selects the entire table.
- `[min]`: Selects the cell with the minimum numerical value in the current selection.
- `[max]`: Selects the cell with the maximum numerical value in the current selection.
- `[find STR]`: Selects the first cell whose value contains the substring `STR`.
- `[_]`: Restores the selection from a temporary variable.

#### Table Structure Modification Commands <a name="table-structure-modification-commands"></a>
Commands for modifying the structure of the table:

- `irow`: Inserts an empty row above the selected cells.
- `arow`: Appends an empty row below the selected cells.
- `drow`: Deletes the selected rows.
- `icol`: Inserts an empty column to the left of the selected cells.
- `acol`: Appends an empty column to the right of the selected cells.
- `dcol`: Deletes the selected columns.

#### Cell Content Modification Commands <a name="cell-content-modification-commands"></a>
Commands for modifying the content of cells:

- `set STR`: Sets the value of the selected cell(s) to the string `STR`.
- `clear`: Clears the content of the selected cell(s).
- `swap [R,C]`: Swaps the content of the selected cell with the cell at row `R` and column `C`.
- `sum [R,C]`: Calculates the sum of values in the selected cells and stores it in the cell at row `R` and column `C`.
- `avg [R,C]`: Calculates the average of values in the selected cells and stores it in the cell at row `R` and column `C`.
- `count [R,C]`: Counts the number of non-empty cells in the selected cells and stores the count in the cell at row `R` and column `C`.
- `len [R,C]`: Calculates the length of the string in the selected cell and stores it in the cell at row `R` and column `C`.

#### Temporary Variable Commands <a name="temporary-variable-commands"></a>
Commands for working with temporary variables:

- `def _X`: Stores the value of the current cell into temporary variable `X`.
- `use _X`: Sets the value of the current cell to the value stored in temporary variable `X`.
- `inc _X`: Increments the numerical value in temporary variable `X`.
- `[_]`: Saves the current selection into the temporary variable `_`, storing only which cells are selected.
