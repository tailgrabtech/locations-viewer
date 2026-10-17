# Locations viewer

A single page that shows a Google Sheet as a searchable, filterable table of locations for the rewards portal.

## Landing page

`https://tailgrabtech.github.io/locations-viewer/` shows a "Choose a partner" dropdown. The list comes from the [directory sheet](https://docs.google.com/spreadsheets/d/1Co6Auh9NkTaH7QTPwQ0PHfZwYhfBWmw4SMprJq-HxmI/edit), which has three columns:

| Partner | Sheet link | Show (Yes/No) |
|---|---|---|
| Name shown in the dropdown | Link to that partner's locations sheet | `No` hides it, for example while the sheet is still empty |

To add a partner, add a row. The directory sheet must also be shared as **Anyone with the link → Viewer**.

## Making a link for a merchant

1. Put the locations in a Google Sheet. Row 1 can hold a title (for example "AROMATHAI SPA CENTERS"). The next row holds the column headers, and each row below it is one location.
2. Share the sheet: **Share → General access → Anyone with the link → Viewer**.
3. Copy the sheet ID from its URL: `https://docs.google.com/spreadsheets/d/<SHEET_ID>/edit`.
4. The portal link is `https://tailgrabtech.github.io/locations-viewer/?sheet=<SHEET_ID>`.

Edits in the sheet appear on the page within a few minutes. Nothing needs to be redeployed.

## Optional link settings

| Add to the link | Effect |
|---|---|
| `&hideTitle=1` | Hides the heading, for pages where the portal already shows one |
| `&title=Some%20Title` | Replaces the heading taken from the sheet |
| `&gid=123456` | Reads a tab other than the first one (copy the `gid=` number from the sheet's URL while that tab is open) |
| `&theme=light` or `&theme=dark` | Forces a colour theme instead of following the device |

## How it behaves

- A column with mostly short, repeated values (City, Locality) gets a dropdown filter. Choosing a City narrows the Locality list.
- A column whose values are all web links (such as Map Link) shows a "View on map" button.
- If Google can't be reached, the page shows the last copy that browser loaded.
