# Import from scratch

The user clicks « Add new » → « Add page » and is offered this view:
![select a widget with external data source](https://github.com/gristlabs/grist-core/assets/371705/1835e49e-997a-49b5-8786-ad11c9d1c4da)

(at least with more cosmetic :sweat_smile:)

They are offered to select a document from their own instance.

About this idea of entering a table URL, that should lead to the same instance or to a public document, I am not sure how difficult it would be to implement that, I would suggest to implement it later if we want to.

Once the user submits, the data are fetched from the external document and put in a new table and a new data source.

Then the user can see the table with synchronized data source:
![left menu with list of tables](https://github.com/gristlabs/grist-core/assets/371705/5d8f3193-4249-44c2-a8f6-45f9881fe0b3)

And the synchronized data source itself:
![synchronized data source](https://github.com/gristlabs/grist-core/assets/371705/e5efabf6-7de8-40ed-8923-41f2d32a46e6)

Both data source list and table list would offer another context menu to synchronize the data source:
![synchronize action in context menu](https://github.com/gristlabs/grist-core/assets/371705/ca662ba2-5be4-4c4a-abf5-763c8c46c675)

And I would suggest that also a click to the 🔁 icon would trigger that action.

When they trigger this action, the user is offered a popup to review the changes and validate if they want to:
![2023-07-20_15-51](https://github.com/gristlabs/grist-core/assets/371705/b2ef24ba-5302-4cde-9613-69a05e2e3e9a)

# Import into an existing table

To be done

# Forget / break the link

To be done
