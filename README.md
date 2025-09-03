📑 Contract Lifecycle Management (CLM) Automation with Workato
This project demonstrates how to build a Contract Lifecycle Management (CLM) intake automation using Google Sheets, Trello, Gmail, and Slack with Workato.
The recipe automatically tracks contract intake requests, creates Trello cards for visibility, and sends notifications when contracts are expiring soon.

🚀 Features
Google Sheets Intake
New contract requests are entered into a Google Sheet (Contract Intake Tracker).

Trello Card Creation
Each new row automatically creates a Trello card containing key contract details (company, dates, amount, owner, etc.).

Conditional Expiry Alerts
If a contract is expiring within 30 days, Workato triggers an urgent alert.

Email Notifications
Sends an email via Gmail to the contract owner with contract details.

Slack Alerts
Posts a formatted message to a Slack channel (e.g., #clm-alerts) with contract information and Trello card link.

⚙️ Workflow Diagram
graph TD
    A[Google Sheets: New Row] --> B[Trello: Create Card]
    B --> C{EndDate < Today+30 days?}
    C -->|Yes| D[Gmail: Send Urgent Email]
    C -->|Yes| E[Slack: Post Expiry Alert]
    C -->|No| F[No Action]
📂 Project Structure
📁 CLM-Intake-Automation
│── 📄 README.md   # Project documentation
│── 📄 sample_contracts.xlsx  # Example contract intake sheet
│── 📄 screenshots/  # Workato recipe setup screenshots
🛠️ Setup Instructions
Google Sheet

Create a sheet with columns: Company, StartDate, EndDate, Amount, OwnerEmail, SourceDealId.

Add test rows for contract requests.

Workato Recipe

Trigger: New row in Google Sheets.

Action 1: Create Trello card with contract details.

Action 2: If EndDate < Today+30 days → send urgent notifications.

Action 3: Send email via Gmail.

Action 4: Post Slack message to alert channel.

Testing

Add a new row in Google Sheets to fire the trigger.

Watch Trello, Gmail, and Slack update automatically.

📸 Screenshots
✅ Workato Recipe Setup

✅ Trello Card Example

✅ Slack Alert Example

✅ Gmail Notification

✅Contract sheet sample


(Screenshots included in /screenshots folder.)

🔮 Future Improvements
Add contract document storage (Google Drive / SharePoint).

Automate renewal workflows with DocuSign or Adobe Sign.

Add advanced conditions (e.g., high-value contracts).

👤 Author
David Antwi
🔗 LinkedIn
💻 GitHub
