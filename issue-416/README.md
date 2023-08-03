# Issue 416

Title: Make reference Data available at Site Level

## Context

Stating @CamilleLegeron

> Hi!
>
> In many cases we need reference data that are the same in all Workspaces of a same Site. For the moment we duplicate each time that reference data in each Workspace, so we have to maintain this master data everywhere.
> An exemple : the list of French cities. We need it in a lot of Workspaces and it's everytime the same list.
>
> It would be great to have a space in the left panel with these master data directly in the root Site.
>
> We imagine that it must not be an easy feature, but it would be very useful for us
>
> (Maybe there is already an issue that we can't find)
>
> @vviers
>
> Camille

## Glossary

<details>
  <summary>Acronyms</summary>
  <dl>
    <dt>MH</dt><dd>Must Have</dd>
    <dt>SH</dt><dd>Should Have<dd>
    <dt>NTH</dt><dd>Nice To Have</dd>
  </dl>
</details>

<details>
  <summary>Vocabulary</summary>
  <dl>
    <dt>Synchronized table</dt><dd>The table which fetches its data from an external table, and gets its data and columns synchronized with this external table</dd>
    <dt>External table</dt><dd>Table of another document of the synchronized table</dd>
  </dl>
</details>

## Acceptance Criteria

- AC1 - MH: A user can create a table whose table is synchronized with an external document
- AC2 - MH: The synchronization is made when the user requests it.
  - AC2.1 - MH: The user sees what data have been changed through a diff
  - AC2.2 - SH: The user also sees what columns are removed or added
- AC3 - MH: A user can convert an existing table to a synchronized one
  - AC3.1 - MH: If another table references a column of the table to synchronize, the reference is not broken if the external table has a column of the same id
  - AC3.2 - SH: If the external table references a column of another table, the synchronized table attempts to lookup locally the same table and the same column using the ids.
  - AC3.3 - MH: The user sees what data have been changed through a diff
  - AC3.4 - SH: The user also sees what columns are removed or added
- AC4 - SH: The user should be able to unlink a synchronized table which would become a simple table;
- AC5 - NTH: A "synchronize every tables" button is offered to the user in the "raw data tables" view;
- AC6 - SH: Edits to synchronized tables should be forbidden;
- AC7 - MH: Attachment columns are not retrieved from source tables;
- AC8 - MH: The hidden columns of the external table are synchronized too;

## Documents

- [design.md](./design.md)
- [technical.md](./technical.md) (TODO)
