The **Extent Calculator** is an online app created in `R` by Kelsey Poloney, hosted on the Archives' [shinyapps site](https://sfuarchives.shinyapps.io/extent_calculator/).
- For code documentation, see the [developer's Github page](https://github.com/kpoloney/extentcalc_shiny).

The Calculator provides an interface for determining an extent in linear metres based on standard box sizes.
- `URC tote box` = 33.33 cm
- `Standard box` [archival container] = 12.5 cm
- `Small box` [small archival container] = 6.5 cm

The linear metre measure is mostly used for textual records. Non-textual records are typically stored in other box types, e.g. `clamshell boxes` (photographs) and `cassette boxes` (audiotapes) or directly to shelf (`map cabinet`). Their extent is more typically expressed as a count of items rather than in linear metres. This is also true of textual records stored flat in `newspaper boxes` or digitally on `optical discs`.
- For more on expressing extents, see the [Data entry guidelines for the AtoM Physical description field](https://github.com/SFU-Archives/atom-guidelines-processing-resources/blob/main/archival-description/physical-description-area.md).

Use the `Complete boxes` section to get the extent of a set of boxes belonging to the same unit (e.g. at the `fonds` level).
- Enter the quantities in the appropriate box fields.
- Click the `Calculate total` button.
- Extents under 1 m will be expressed in cm; otherwise extents are given in metres.

Use the `Partial boxes` section at the `series` level where there is no 1-to-1 relationship between the series and the box.
- One `series` can spread across several `boxes` and one `box` can include `files` from several `series`.

For a `box` shared by several `series`:
- Select the `type of box` (gets the `total box size`).
- Enter the total number of `files` in the box (gets the `average file size` for that box).
- Enter the number of files from the target series in the box (multiples by `average file size` to get the `total extent`).

For example, in a typical scenario `series x`:
- Begins in a box shared with another series (`shared box 1`).
- Has a number of its own `complete boxes` not shared with another series.
- End in a box shared with another series (`shared box 2`).
- Use `Shared box 1` and `Shared box 2` for the beginning and end boxes and `Complete boxes` for the boxes it does not share to get the total series extent.

This method assumes all files in a box are roughly the same size (= `average file size`).
- This is not always the case, but it gives a good ballpark estimate that can manually revised as needed for outliers.

## Links
- [Online app](https://sfuarchives.shinyapps.io/extent_calculator/)
- [Developer's Github site](https://github.com/kpoloney/extentcalc_shiny)

## Screenshot
![](https://github.com/SFU-Archives/digital-repository-utilities/blob/master/screenshots/extent-calculator.png)

```
Last updated: Nov 30, 2023
```
