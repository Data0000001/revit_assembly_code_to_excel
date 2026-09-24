# Assembly Code to Excel

Converts Revit assembly code files (`.txt`, Revit Assembly Code format) into a formatted Excel workbook. It is a single HTML file, so there is nothing to install.

## How to use

1. Open `assembly_code_to_excel.html` in a browser.
2. Click **Choose files** or drag one or more `.txt` files onto the page.
3. The `.xlsx` downloads automatically, with the same name as the source file.

**Show issues** lists any problems found in the file.

The tool works offline. Files are processed locally in the browser and are never uploaded.

## Output

| Sheet | Contents |
|---|---|
| **Classifier** | Names are indented by level, levels 1–3 are shaded with colore, and rows are grouped so levels can be collapsed. Filter and frozen header are on. |
| **Summary** | Source file, total rows, issue count, and number of codes in each top-level section. |
| **Issues** | Source line number, code, name and description for each problem found. |

## Checks

The tool reports the following problems:

- empty code or empty name;
- code not in `NN.NN.NN` format;
- level that is not a number or doesn't match the code depth;
- duplicate codes;
- missing parent code;
- unmatched quotation marks;
- names split across lines (merged automatically);
- extra columns.

When a code is empty, the tool suggests the probable code based on the next row. The source data is never changed.
