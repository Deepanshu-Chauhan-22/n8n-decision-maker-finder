# 👤 AI Business Decision Maker Finder

An AI-powered contact enrichment pipeline built with **n8n**, **Hunter.io**, and **Google Sheets** that automatically discovers decision-makers, professional email addresses, and LinkedIn profiles for existing business leads.

---

# 🚀 Overview

After generating a list of businesses, the next challenge is identifying the right person to contact.

This workflow automates the enrichment process by reading businesses from Google Sheets, searching for decision-makers using Hunter.io, extracting professional contact information, and updating the spreadsheet with structured outreach-ready data.

The pipeline is designed for outbound sales, lead generation, and cold outreach automation.

---

# ✨ Features

- Automatically reads business leads from Google Sheets
- Searches company domains using Hunter.io
- Finds decision-makers within each company
- Extracts professional email addresses
- Extracts LinkedIn profiles (when available)
- Updates the original spreadsheet automatically
- Handles multiple decision-makers
- Wait node for API rate limiting
- Fully automated in n8n

---

# 🏗 Architecture

```
                    Google Sheets
                 (Business Leads)
                         │
                         ▼
                Read Unprocessed Leads
                         │
                         ▼
                  Hunter Domain Search
                         │
                         ▼
                Find Decision Makers
                         │
              ┌──────────┴──────────┐
              │                     │
        Contacts Found        No Contacts
              │                     │
              ▼                     ▼
     Extract Email & LinkedIn   Update Status
              │
              ▼
      Write Results to Google Sheets
```

---

# 📂 Repository Structure

```
.
├── workflow
│   └── Finding person email using hunter.json
│
├── images
│   ├── finding person workflow.png
│   └── sample output.png
│
├── README.md
└── LICENSE
```

---

# ⚙ Workflow Breakdown

### 1. Read Business Leads

- Reads businesses from Google Sheets
- Processes only businesses that have not been enriched

---

### 2. Company Lookup

- Uses Hunter.io Domain Search
- Retrieves company information
- Searches available contacts

---

### 3. Decision Maker Extraction

Extracts information such as:

- First Name
- Last Name
- Job Title
- Professional Email
- LinkedIn Profile
- Confidence Score 

---

### 4. Data Processing

- Filters valid contacts
- Handles multiple contacts per company
- Waits between requests to respect API limits

---

### 5. Google Sheets Update

Automatically updates the spreadsheet with:

- Decision Maker Name
- Position
- Email Address
- LinkedIn Profile
- Processing Status

---

# 🛠 Technologies Used

- n8n
- Hunter.io API
- Google Sheets
- REST APIs

---

# 📸 Workflow

Workflow image:

`images/finding person workflow.png`

---

# 📊 Sample Output

Each processed business is enriched with contact information such as:

| Business | Decision Maker | Position | Email | LinkedIn |
|-----------|---------------|----------|--------|----------|
| ABC Roofing | John Smith | Owner | john@abcroofing.com | linkedin.com/in/johnsmith |

Example output is available in:

`images/sample output.png`

---

# 🔧 Setup

1. Import the workflow into n8n.
2. Configure the required credentials:
   - Google Sheets
   - Hunter.io API
3. Update the spreadsheet IDs.
4. Execute the workflow.

---

# 💡 Use Cases

This workflow is ideal for:

- Cold Email Outreach
- Sales Prospecting
- Lead Enrichment
- Agency Lead Generation
- CRM Population
- B2B Prospecting

---

# 📈 Future Improvements

- Apollo.io integration
- LinkedIn scraping fallback
- AI contact verification
- Multi-provider enrichment
- CRM integrations
- Automatic email validation
- Contact scoring

---

# 📄 License

This project is licensed under the MIT License.

---

# 👨‍💻 Author

**Deepanshu Chauhan**

If you found this project useful, consider giving it a ⭐ on GitHub.