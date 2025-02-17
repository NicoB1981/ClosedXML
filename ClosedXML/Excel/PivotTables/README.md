# Invariants

Pivot table invariants that often cause Excel repair/crash:

Repair:
* When a field is in `pivotTableDefintion.dataFields` collection <=> `pivotField.dataField` is set.
* When a field is in `pivotTableDefintion.rowFields` collection => `pivotField.axis` must be set to `axisRow`.
* When a field is in `pivotTableDefintion.colFields` collection => `pivotField.axis` must be set to `axisCol`.
* When a field is in `pivotTableDefintion.pageFields` collection <=> `pivotField.axis` must be set to `axisPage`.
* When pivot table has a page fields, but ref specifies an area that doesn't have enough space above it to fit the page fields.

Crash:
* `pivotField` doesn't contain even `default` item, but is used in other an axis (row/col/page).
* axis fields can't contain `ΣValues` field If there is only one `pivotTableDefintion.dataFields`, 
* If `pivotTableDefintion.rowFields` or `pivotTableDefintion.colFields` reference `ΣValues` field, the `dataPosition` must be set.
