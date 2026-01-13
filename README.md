**AI-Powered Inventory Monitoring & Alert Automation**
This project contains an n8n automation workflow that monitors inventory levels from Google Sheets and automatically sends AI-generated low-stock alert emails using Gmail.
The workflow runs on a schedule, checks current stock against threshold values, and uses an AI Agent (Google Gemini) to generate a professional alert message when items are running low.

**What this automation does**
- Runs automatically every week
- Reads inventory data from Google Sheets
- Compares Stock vs Threshold
- Filters items that are below threshold
- Aggregates all low-stock items
- Uses an AI Agent (Google Gemini) to generate a formatted alert
- Sends a low-stock alert email via Gmail

**Workflow Architecture**
1.Schedule Trigger - Runs weekly (Monday at 9 AM)
2.Google Sheets(Get Rows) - Reads inventory data from a spreadsheet
3.Filter - Keeps only items where: Stock < Threshold
4.Aggregate - Combines all low-stock items into one dataset
5.AI Agent (Google Gemini + Memory) - Generates a professional alert message such as:
ALERT ALERT - LOW STOCK ALERT:
  - Item A : 3 left (need 10). Recommend reordering from Supplier X
  - Item B : Out of Stock (need 5). Recommend reordering from Supplier Y
6.Gmail Tool -- Sends the alert email automatically

**TECH STACK**
- n8n – Workflow automation
- Google Sheets API – Inventory data source
- Google Gemini Chat Model – AI message generation
- LangChain AI Agent – Reasoning & formatting
- Gmail API – Email alerts
- Simple Memory Buffer – Session context

**DATA REQUIREMENTS**
Your sheet should contain columns like:
- Item Name
- Stock
- Threshold
- Supplier
- The workflow automatically evaluates:
- Stock < Threshold

**BUSINESS USE CASES:**
- Restaurant or warehouse inventory monitoring
- Automated procurement alerts
- Supply chain risk prevention
- AI-driven operational reporting
- Smart operations dashboards

**How to use this workflow :**
 - Import the JSON into n8n
 - Connect credentials:
 - Google Sheets OAuth
 - Google Gemini API
 - Gmail OAuth
Update:
 - Spreadsheet ID
 - Email recipient
 - Activate the workflow

**Workflow Architecture**
![Workflow.png](workflow.png)

