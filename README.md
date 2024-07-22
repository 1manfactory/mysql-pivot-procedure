# MySQL Pivot Procedure

This repository contains a MySQL/MariaDB stored procedure to create a pivot table dynamically. The procedure allows you to summarize data from a table by converting unique values from one column into multiple columns in the output.

## Procedure Overview

The procedure `pivot_procedure` takes various parameters to dynamically create a pivot table. Here is the complete SQL code for the procedure:

## Parameters

- `P_Column_Field`: The column to be pivoted.
- `P_Value`: The column to aggregate.
- `P_From`: The source table.
- `P_Where`: The WHERE clause for filtering data.
- `P_Collimit`: The maximum number of columns to pivot.
- `P_Row_Field`: The column for grouping rows.
- `P_Rowsumname`: The name of the column for row sums.
- `P_Orderby`: The column to order the results.
- `P_Savetable`: The name of the table to save the results.

## Usage

To use this procedure, you need to call it with the appropriate parameters. Here's an example:

```sql
CALL pivot_procedure(
    'Shop',      -- P_Column_Field
    'Amount',    -- P_Value
    'sales',     -- P_From
    '1=1',       -- P_Where
    10,          -- P_Collimit
    'Date',      -- P_Row_Field
    'Total',     -- P_Rowsumname
    'Date',      -- P_Orderby
    ''           -- P_Savetable
);
```

This will pivot the `sales` table, grouping by `Date` and pivoting on the `Shop` column with the sum of `Amount`.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Feel free to submit pull requests or open issues to improve this procedure.

## Acknowledgements

Inspired by various SQL pivot table techniques and community contributions.
