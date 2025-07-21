*High Priority*
- [x] Collapsible menu
- [x] Rearrangeable ~~cards~~ elements
- [x] edit button
- [x] error handling (partial)
- [x] responsive design (partial)
- [x] polish
- [x] API calls & storage
	- [x] fetch view 
	- [x] extract tallyOrder & histogramOrder
	- [x] make memoized tally and histogram Chart arrays based on the Order in which their ID's occur in tallyOrder and histogramOrder
	- [x] initialize tallyOrderItems & histogramOrderItems to previous arrays
	- [ ] (Optional) Remove tallyOrderItems & histogramOrderItems from logic, use base arrays instead
- [x] fix view edits UI updates only working the first time
- [x] fix POST state reversion bug
- [ ] fix flickering state reversion bug
- [x] new chart type
	- [x] implement mock combo chart
	- [x] add real datapoints
	- [x] integrate into chart addition form
	- [x] integrate into chart ordering system
- [x] add support for multiple data sources
- [x] tallyboard for Total flow rate and overall
- [ ] tallyboard and histogram for plant efficiency
- [ ] revamp edit button
	- [ ] make edit button display drag handle and pencil icons
	- [ ] setting icon instead of "edit"

*Medium Priority*
- [x] scrollable sidemenu
- [x] adjust mobile view
- [ ] Date picker

*Low Priority*
- [x] fix flickering when dragging items
- [ ] list type data sources based on location

```
updated view type
{
...View,
tallyOrder: [ tallyChart1, tallyChart2, tallyChart3],
histogramOrder: [histogram1]
updatedAt: UTCDate
}
```

New Chart type
![[Screenshot_20250711_112415.png]]

### EFFICIENCY
production flow rate = raw flow rate = 100% efficiency