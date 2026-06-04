MPG Multi-Study Downtime Totalizer
A standalone HTML-based downtime analytics tool for combining multiple saved MPG downtime study JSON files into a single multi-study downtime summary, Pareto analysis, production calculation view, and printable/exportable reporting package.
The app runs entirely in the browser and does not require a server, database, Excel macros, or external dependencies.
---
Purpose
The MPG Multi-Study Downtime Totalizer is used to consolidate downtime data from multiple saved downtime-study JSON files. It helps teams compare studies, identify the highest downtime contributors, filter or group reason codes, and export combined reporting for review.
Primary use cases include:
Combining multiple downtime studies into one reason-code Pareto
Comparing downtime across locations, shifts, lines, or individual study files
Reviewing total downtime, observed time, downtime percentage, and production loss
Grouping related downtime tags into higher-level categories
Exporting combined study data for Excel review
Printing a simplified Pareto PDF for supervisor or stakeholder review
---
Key Features
Multi-Study JSON Loading
The app accepts saved MPG downtime study files in `.json` format.
Supported loading options:
Select multiple JSON files
Drag and drop JSON files
Load all JSON studies from a folder
Drop a parent folder containing multiple JSON studies
The app rejects non-JSON files and keeps loaded studies active until the user clears them.
---
Combined Downtime Pareto
The main analysis section builds a combined downtime Pareto across all loaded studies.
The Pareto summarizes:
Reason code
Code description
Event count
Total downtime
Downtime minutes
Percent of total downtime
Cumulative percent
Number of studies affected
Rows can be expanded to review the timing records behind each reason-code total.
---
Summary Metrics
The dashboard includes high-level metrics for the loaded study set:
Studies loaded
Downtime events
Total downtime
Observed time
Downtime percentage
These metrics update automatically when studies are loaded, filtered, grouped, or cleared.
---
Pareto Study Slicer
The study slicer allows the user to change the Pareto source view.
Available filters include:
All matching studies
Individual study file
Location
Shift
Study sort mode
The slicer also displays view-specific production reference metrics, including:
View events
View downtime
View share
Optimum production count
Production loss count
Utilization from production
---
Reason-Code Filtering
The reason-code filter allows users to select which tags are included in the Pareto.
Users can:
Include or exclude individual reason codes
Select all tags
Clear all tags
Keep tags loaded but excluded from chart and export totals
Unchecked tags remain loaded but are excluded from the active Pareto view.
---
Pareto Tag Grouping
The tag grouping section allows users to combine related downtime tags into grouped categories.
Users can:
Create named grouping rows
Drag reason-code tags into groups
Control grouped tags from the group row
Export tag groups as a CSV
Import tag group CSV files
Clear grouping rows
Remove empty groups
Grouping is useful when individual tags should be rolled up into broader categories such as:
Robot / Automation
Material Handling
Transfer Section
Feeder Issues
Quality / Inspection
Setup / Changeover
---
Data Calculation Tab
The Data Calculation Tab provides a production-focused view by loaded file.
Calculated values include:
Production speed
Observed time
Observed hours
Downtime total
Downtime hours
Projected production
Production loss
Net available production
Downtime percentage
The calculation logic is:
```text
Projected Production = Production Speed × Observed Hours
Production Loss = Production Speed × Downtime Hours
Net Available Production = Projected Production − Production Loss
```
---
Loaded Study Reference
The Loaded Study Reference table preserves source information from each imported study.
Tracked reference fields include:
File name
Location
Date
Shift
Line / machine
Product
Observer
Study time
Time source
Total downtime
Downtime percentage
Production speed
Projected units
Lost units
This section helps maintain traceability between combined Pareto results and the original studies.
---
Export and Print Options
The app includes reporting options for further review:
Export Excel: Exports the combined downtime and production analysis into an Excel-compatible file.
Print Pareto PDF: Prints a simplified Pareto report for supervisor or stakeholder review.
Export Group CSV: Exports custom tag grouping definitions for reuse.
Import Group CSV: Imports grouping definitions for consistency across studies.
For best PDF appearance, enable Background graphics in the browser print dialog.
---
Recommended Workflow
Open the HTML file in a modern browser.
Load saved MPG downtime study JSON files.
Review the combined summary metrics.
Use the slicer to isolate all studies, one study, a location, or a shift.
Use the reason-code filter to include or exclude specific downtime tags.
Create tag groups if related tags should be combined.
Review the combined Pareto chart and Pareto table.
Review the Data Calculation Tab for production impact.
Review the Loaded Study Reference table for traceability.
Export Excel or print the Pareto PDF.
---
Browser Compatibility
Recommended browsers:
Microsoft Edge
Google Chrome
Supported but may vary by device:
Safari
Firefox
Mobile Chrome
Mobile Safari
Folder loading works best in Chromium-based browsers such as Edge and Chrome.
---
Input File Requirements
The app is designed to read saved MPG downtime study JSON files.
Each JSON study should include event records with:
Downtime reason code
Duration in seconds
Start timestamp or time reference
Stop timestamp or time reference
Optional notes
Optional study metadata
Optional production speed
Optional study timing segments
The app can still calculate partial results if some optional metadata is missing, but reporting quality improves when study files include complete study information.
---
Deployment Options
Because this is a static HTML app, it can be deployed through any static hosting method.
Recommended options:
GitHub Pages
SharePoint
OneDrive shared link
Internal company web server
Local HTML file
Company intranet
For mobile use, hosting the file through a secure HTTPS link is recommended. Users can then add the page to their iOS or Android home screen.
---
Data Privacy
The app runs locally in the user’s browser. Loaded JSON files are processed client-side. No data is sent to a server unless the HTML file is modified to do so or hosted with additional backend functionality.
Users are responsible for saving exported reports or preserving source JSON study files.
---
Known Limitations
This is a static browser-based tool, not a database-backed application.
Data is not permanently stored unless exported or saved externally.
Folder loading may not work in all browsers.
PDF output depends on browser print settings.
Excel export is browser-generated and may vary slightly by Excel version.
The app expects JSON files produced by the MPG downtime study workflow.
---
Suggested Repository Structure
```text
downtime-totalizer/
├── index.html
├── README.md
└── sample-data/
    └── sample-study.json
```
Use `index.html` as the main GitHub Pages entry file.
---
Recommended GitHub Pages Setup
Rename the HTML file to `index.html`.
Add `index.html` and `README.md` to the repository.
Go to Settings > Pages.
Select Deploy from branch.
Choose the `main` branch and `/root` folder.
Save.
Use the generated HTTPS link to access the app.
---
Maintenance Notes
When updating the app:
Keep a backup of the previous HTML version.
Replace `index.html` with the new version.
Update this README if major features change.
Test with at least one known-good JSON study file.
Confirm Excel export and PDF print still work as expected.
---
Project Status
Current status: standalone browser-based downtime analytics utility.
The app is intended to support process improvement, downtime review, and stakeholder reporting by consolidating multiple downtime studies into a single actionable view.
