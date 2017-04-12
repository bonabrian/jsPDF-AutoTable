# BEFORE RELEASE
- Go through events and see if they make change
- Write new example showcasing events (adding images, cell styles etc)
- Change events back to callbacks/hooks if possible. It is a unessessary change (?). Have seen other libraries using 
callbacks like that now. But check out how other libs are doing it. Good examples probably are graphing libs. D3? Charts?

# Changelog

### 3.0
- Changed initialization to `doc.autoTable({head: ..., body: ...})`
- Changed from hooks to eventHandler
- Changed getting previous autoTable to `doc.previousAutoTable`
- Changed default overflow method to linebreak (previously it was ellipsize)
- Changed `rowHeight` style to `minCellHeight`
- Changed `columnWidth` style to `cellWidth`
- Added native rowspan and colspan support
- Added `fromHtml: HTMLTableElement|string`. If set to string it should be a css selector pointing to a table element.
- Added `useCss: boolean` option which decides if css styles should be used when using fromHtml.
- Added `includeHiddenHtml: boolean` option. Used with fromHtml.
- Added `showFoot` option (similar to showHead)
- Added `footStyles` option (similar to headStyles)
- Added `avoidRowSplit` option
- Renamed `pageBreak` option to `avoidTableSplit`
- Renamed headerStyles to headStyles
- Renamed showHeader to showHead

Deprecations:
- The old initialization `doc.autoTable(columns, data, options)` is now deprecated. 
- Deprecated `doc.autoTableHtmlToJson()` in favour of fromHtml option
- Hooks are deprecated in favour of eventHandler
- Old way of getting previous autoTable: `doc.autoTable.previous`
- Use avoidPageSplit instead of pageBreak
- Add new page manually before calling autoTable instead of using pageBreak: always

Migrating to version 3.0 should be rather painless as most changes are backward compatible. 
Some large changes were made however so write an issue if you encounter any problems.

Note that the support for the deprecations listed above will be removed in a the next major version.