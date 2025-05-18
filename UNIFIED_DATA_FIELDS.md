# Unified XLSX Data Structure Fields

The table below lists common fields used in a unified data model that combines information from **ExcelJS** (front end) and **Apache POI** (back end). The **Source** column indicates whether the field exists in both libraries, or only in one of them.

| Field | Source | Purpose |
|------|------|---------|
| `creator` | Both | Document creator metadata. |
| `lastModifiedBy` | Both | Last person to modify the workbook. |
| `created` | Both | Timestamp for when the document was created. |
| `modified` | Both | Timestamp for the last modification. |
| `properties.title` | Both | Workbook title. |
| `properties.subject` | Both | Workbook subject. |
| `properties.keywords` | Both | Keywords or tags for searching. |
| `properties.category` | Both | Category metadata. |
| `properties.description` | Both | Description of the workbook. |
| `worksheets[].id` | Both | Numeric sheet identifier (1-based). |
| `worksheets[].name` | Both | Visible sheet name. |
| `worksheets[].views` | Both | Sheet view settings such as zoom and active cell. |
| `worksheets[].dimensions` | Both | Worksheet row/column extents. |
| `worksheets[].tabColor` | Both | Color of the sheet tab. |
| `worksheets[].pageSetup` | Both | Print-related settings (paper size, orientation, etc.). |
| `worksheets[].pageMargins` | Both | Margins used for printing. |
| `worksheets[].properties` | Both | Miscellaneous sheet properties (default row height, outline levels). |
| `worksheets[].merges` | Both | Ranges that have been merged. |
| `worksheets[].dataValidations` | Both | Data validation rules for the sheet. |
| `worksheets[].conditionalFormattings` | Both | Conditional formatting rules. |
| `worksheets[].images` | Both | Image definitions added to the sheet. |
| `rows[].number` | Both | Row index (1-based). |
| `rows[].height` | Both | Custom row height. |
| `rows[].hidden` | Both | Whether the row is hidden. |
| `rows[].outlineLevel` | Both | Outline level for collapsing rows. |
| `cells[].address` | Both | Address such as `A1`. |
| `cells[].type` | Both | Cell data type (string, number, etc.). |
| `cells[].value` | Both | Cell value. |
| `cells[].formula` | Both | Formula expression if present. |
| `cells[].result` | Both | Cached result of a formula. |
| `cells[].hyperlink` | Both | Hyperlink associated with the cell. |
| `cells[].richText` | Both | Rich text segments in the cell. |
| `cells[].style` | Both | Number format, fonts, alignment, borders, fill, etc. |
| `cells[].dataValidation` | Both | Validation rule applied to the cell. |
| `cells[].comment` | Both | Cell comment or note. |
| `cells[].protection` | Both | Cell-level protection flags. |

`Both` indicates that ExcelJS and POI expose similar fields or APIs. When only one side exposes a field, it should be marked accordingly (e.g., `ExcelJS only`).

This structure enables the front end and back end to share a complete view of an XLSX workbook. After parsing the same file, each side populates the same fields so that any logical operation can work on identical JSON data.

