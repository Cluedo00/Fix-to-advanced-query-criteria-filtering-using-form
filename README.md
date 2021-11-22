# Fix-to-advanced-query-criteria-filtering-using-form
Fix to advanced query criteria filtering using form

Problem:
Hi

I have a subfrom based on a query. the Subform has multiple combo box and text filtering options. I want the query to be filtered because it is used other places in the “MainForm” . If there is a better option than using query criteria I am happy to hear it.

How it should work:

The user can search using a combination of text or combo box. If the user has nothing selected in the combo or text boxes, all record will show.

If a User selects (“AV” in ToolType combobox) and (Type “4” in SN textbox) and (selects “Mechanic” in ToolBox). All the record with these parameters will show.

Problem:

So far, the filtering only works on one combo box. If I try to add all the combo and text boxes to the filtering criteria it doesn’t work. The query shows no records.

Below is the Text box and Query “Code”


Solution:

I found the solution!!

The solution was to add all the criteria at the same time, and then run the query.

Earlier I would add one criteria at a time, then run the query to see if it worked, then go back to Design View and add the next criteria. 

Apparently this influences how Access arranges the SQL code for the query.

In the SQL below I only filtered two fields (ToolBox and ToolType) with comboboxes ([PrintList_ToolType_FilterCB] and [PrintList_ToolBox_FilterCB]). This was to make it simpler to understand.

After I found out it was working. I later added the criteria to all the fields I wanted to filter. And I added them all at the same time. Then access created 1815 lines of SQL code for the query that works perfectly!!
