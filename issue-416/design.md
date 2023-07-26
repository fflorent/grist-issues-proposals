# Import from scratch

The user clicks « Add new » → « Add page » and is offered this view:

![select a widget with external table](https://github.com/gristlabs/grist-core/assets/371705/1835e49e-997a-49b5-8786-ad11c9d1c4da)

They are offered to select a document from their own instance.

About this idea of entering a table URL, that may be implemented as a NTH enhancement, after the rest of the feature is implemented.

Once the user submits, the data are fetched from the external document and put in a new table and in a new page.

Then the user can see the synchronized table:

![left menu with list of tables](https://github.com/gristlabs/grist-core/assets/371705/5d8f3193-4249-44c2-a8f6-45f9881fe0b3)

And also the synchronized raw table:

![synchronized raw data tables](https://github.com/gristlabs/grist-core/assets/371705/e5efabf6-7de8-40ed-8923-41f2d32a46e6)

Both raw tables list and page list would offer another context menu to synchronize the table:

![synchronize action in context menu](https://github.com/gristlabs/grist-core/assets/371705/ca662ba2-5be4-4c4a-abf5-763c8c46c675)

In case one synchronized table is rendered in a page, the 🔁 icon would appear.

And I would suggest that also a click to the 🔁 icon would trigger that action.

When they trigger this action, the user is offered a popup to review the changes and validate if they want to:

![2023-07-20_15-51](https://github.com/gristlabs/grist-core/assets/371705/b2ef24ba-5302-4cde-9613-69a05e2e3e9a)

# Import into an existing table

Use case: a user used to copy tables from a document to another, and wants to synchronize the data (NB: one-way synchronization).

![Contextual menu of raw table with *Initiate a synchronization*](https://github.com/fflorent/grist-issues-proposals/assets/371705/9f0e7dd1-97e2-4093-87c5-a89e9d4092f4)

Then the user is offered the same popup to validate the changes:

![2023-07-20_15-51](https://github.com/gristlabs/grist-core/assets/371705/b2ef24ba-5302-4cde-9613-69a05e2e3e9a)

The user also sees what columns are removed and what columns are added:

**TODO** (not implemented in snapshots comparisons)

# Desynchronize a document

The user would be offer a "Remove synchronization" item in the contextual menu of a synchronized raw data table

![contextual menu of a synchronized table](https://github.com/fflorent/grist-issues-proposals/assets/371705/4b5a14a8-13c7-48d5-9dfd-d2c718db7973)

# Synchronize every tables

The user would be offer the "Synchronize every tables" in the raw data tables:

!["synchronize every tables" button at the bottom of the raw data tables list](https://github.com/fflorent/grist-issues-proposals/assets/371705/4f53abdb-db9a-419d-a663-4d60c665dd86)
