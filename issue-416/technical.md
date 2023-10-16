# Technical proposal

## API

3 new APIs are introduced:
 - `POST /api/docs/:docId/tables/:tableId/source` to allow attaching a source to a table
   - passed data:
     - in the query, `:docId` and `:tableId` refer to the target (synchronized) document / table;
     - in the body, 2 properties are passed: `docId` and `tableId`, which are the reference to the source table ;
   - pre-conditions:
     - the table should not have any source yet (a target table may have only 1 source table, although a source table may have multiple target tables) ;
     - the passed data reference existing tables in the same site (or even instance?);
     - the source table id is not taken in the target document by another table
   - What it does:
     - it stores the `docId` and the `tableRef` within the document (`_grist_Source_table`);
     - it copies the id of the source table to the target one;
 - `DELETE /api/docs/:docId/tables/:tableId/source` to allow detaching a source to a table
   - passed data:
     - in the query, `:docId` and `:tableId` refer to the target (synchronized) document / table;
   - pre-conditions:
     - the synchronized table should have a source table;
   - What it does:
     - it removes the `docId` and the `tableRef` from the document;
 - `POST /api/docs/:docId/tables/:tableId/sync` to trigger the synchronization
   - passed data: none
   - pre-conditions:
     - the synchronized table should have a source table;
     - it ensures that the table id of the source table corresponds to the target table (if it does not, it may break formulas, so the API user should change the id of the target table);
   - What it does:
     - it replaces the synchronized table columns with the source table ones:
       - it fetches the columns from the source table;
       - it filters out the attachment columns;
       - for the reference columns:
         - if the referenced column belongs to another table, it should be a synchronized table (otherwise rejects) and the referenced table gets synchronized beforehand;
         - displayCol + visibleCol => it maps the column ids of the source document with the ones of the target document
       - it also transforms the "rules" fields (FIXME: HOW? more details needed)
     - it replaces the synchronized table data:
       - it fetches the data from the source table;
       - it filters out the data from the formulas;
       - for each reference column (whose values are row ids), it maps the column ids of the source document with the ones of the target document;
