# Viva Connections 'Work Anniversaries' Card

![image](https://github.com/alexc-MSFT/viva-connections-workanniversaries-card/assets/12395485/9b0d3e60-b006-4a7a-99e5-e464dd3d66de)

A low-code card built with the Card Designer that uses the new Advanced API Features (https://learn.microsoft.com/en-us/sharepoint/dev/spfx/viva/features/card-designer/card-designer-api-support) to display work anniversaries for employees.

It uses the SharePoint REST API and a SharePoint list.

It is designed to be part of a wider 'Work Anniversary' solution utilising a Power Automate flow to send adaptive cards on employee anniversaries however this has not been built yet. This is something I will build at a later date.

To deploy the solution as is, follow the steps below:

1. Configure the new Advanced API Features by following the steps in the documentation above.
2. Create a SharePoint list in your Viva Connections home site named 'WorkAnniversaries' with the following columns:

   - NoOfYears (Number)
   - Employee (Person or Group)
   - Employee Name (Single line of text)
   - Hire Date (Date)
   - Profile Photo URL (Hyperlink)
   - WeekCommencing (Date)

   Populate the list with some example list items. The 'WeekCommencing' column should be the date on which the current week commences. **The card displays all items from the list currently, the idea being a Power Automate flow would clear these down weekly.**

3. Add a Card Designer card to your dashboard and configure it as follows:

- Card Size: Medium
- Title: Anniversaries
- Icon: Balloon
- Heading: View upcoming work anniversaries
- Image: Use the image supplied in this repo
- Card action: Show the quick view
- Template JSON: Copy and paste the provided template JSON from this repo
- Data source: Call a SharePoint API
- Request URL: lists/GetByTitle('WorkAnniversaries')/items

4. Apply the changes to the card and republish your dashboard.
5. Clicking on the card should show the quick view and the items from your list.
