

*1. Project Title / Headline (3-4 lines)*
Sales Automation: Dynamic Email & WhatsApp Follow-Up System
AI-Powered Lead Nurturing for ISO Certification Renewals
Automating Personalized Proposal Expiry Reminders at Scale
*2. Short Description / Purpose*
An n8n automation built for Exercise 1 that eliminates manual follow-ups. It imports customer data from Google Sheets, dynamically generates personalized ISO renewal emails (ISO 9001, 14001, 20001, 45001) using an AI Agent, and triggers automated email + WhatsApp delivery in one click, ensuring no proposal expiry is missed.

*3. Tech Stack*
- *Automation:* n8n (Workflow Engine)
- *AI Layer:* AI Agent + OpenAI Chat Model + Simple Memory
- *Email:* Gmail API (Send a message1)
- *WhatsApp / SMS:* Twilio API (HTTP Request + Send an SMS/MMS/WhatsApp node)
- *Trigger:* When chat message received

*4. Data Source*
Google Sheets as primary CRM:
Columns: `Company Name | Service (ISO Type) | Contact Person Name | Contact Person Email`
- 5 sample records: Santosh Chemical, Paritosh Engineering, Sintrex Fertilizers, etc.
- Data fetched via `Get row(s) in sheet` node (5 items total)
- Dynamic fields: `{{ $json.Service }}` and `{{ $json.Contact_Name }}` used in template

*5. Features and Highlights*

*5.1 Business Problem*
Sales team was manually tracking ISO proposal expiry (2 months before) and typing individual emails. Time-consuming, errors in name/service, and missed follow-ups leading to lost renewals.

*5.2 Goal of the Dashboard / Workflow*
Build a one-time template that auto-personalizes and auto-sends: `Hello Mr. [Name], Your [Service] proposal is expiring...` without rewriting. Bonus: Add WhatsApp for higher open rate.

*5.3 Walk Through the Key Visuals*
- *Trigger (When chat received - 1 item):* Starts the flow.
- *AI Agent + OpenAI + Memory:* Generates personalized pitch content.
- *Get row(s) in sheet:* Reads 5 leads from Sheet.
- *Send a message1 (Gmail):* Sends 5 personalized emails `send: message`.
- *HTTP Request:* `POST: https://api.twilio.com/...` - Prepares WhatsApp payload.
- *Send an SMS/MMS/WhatsApp:* Final delivery via Twilio `send: sms`.

*5.4 Highlight the Insights*
Workflow executes 100% green with 5 items branched. Dynamic insertion logic works for all ISO types. AI Agent ensures tone is professional, not generic. Single template serves multiple services as required in PDF.

*5.5 Show the Business Impact*
- 90% time saved - 5 emails + 5 WhatsApp in <30 sec vs 30 mins manual
- Zero error in personalization
- Scalable to 1000s of rows
- Dual-channel (Email + WhatsApp) increases renewal conversion
- Meets all Exercise 1 requirements + valuable add-on feature

HERE IS WORKFLOW IMAGE LINK =

https://github.com/rajkishordash50/SALES-AUTOMATION---DYNAMIC-EMAIL-WHATSAPP/blob/main/WhatsApp%20Image%202026-08-25%20at%207.04.31%20AM%20(1).jpeg
