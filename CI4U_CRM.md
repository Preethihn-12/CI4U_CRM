# Define variables
GITHUB_USERNAME="your-username"
REPO_NAME="sales-lead-tracker"
CLONE_URL="https://github.com/$GITHUB_USERNAME/$REPO_NAME.git"

# Clone the empty GitHub repo
git clone $CLONE_URL
cd $REPO_NAME

# Create folders
mkdir templates sample-data 

# Create README.md and insert Markdown table
cat <<EOF > README.md
# 🚀 Sales Lead Tracker

This repository is designed for sales representatives to track and manage customer leads effectively.

## 📊 Lead Table Format

| Lead Status | UIN | Date Added | Company Name | Contact Number | Location | Lead Source/Link | Out-Reach Status | Outreach Note | Client Name | WhatsApp Number | Email | Response | Date | Time | Meeting Link | Next Follow-up Date | Follow-up Note | WhatsApp Link Output | Email Link Output | Scope of the Work | Quotation (INR) | Approved Quotation (INR) | WON (Yes/No) |
|-------------|-----|------------|--------------|----------------|----------|------------------|------------------|----------------|-------------|------------------|-------|----------|------|------|---------------|----------------------|----------------|----------------------|--------------------|--------------------|------------------|----------------------------|---------------|
|             |     |            |              |                |          |                  |                  |                |             |                  |       |          |      |      |               |                      |                |                      |                    |                    |                  |                            |               |
EOF

# Create lead-entry-template.csv
cat <<EOF > templates/lead-entry-template.csv
Lead Status,UIN,DATE ADDED,COMPANY NAME,Contact Number,LOCATION,LEAD SOURCE/LINK,OUT-REACH STATUS,OUTREACH NOTE,CLIENT NAME,WHATSAPP NUMBER,EMAIL,RESPONSE,DATE,TIME,Meeting Link,NEXT FOLLOUP DATE,FOLLOUP NOTE,WhatsApp Link Output,Email Link Output,Scope Of the work,Quotation INR,APPROVED QUOTATION INR,WON (Yes/No)
EOF

# Create sample markdown file (optional)
cat <<EOF > sample-data/sample-leads.md
## 📦 Sample Lead Entries

| Lead Status | UIN | Date Added | Company Name | Contact Number | Location | Lead Source/Link | Out-Reach Status | Outreach Note | Client Name | WhatsApp Number | Email | Response | Date | Time | Meeting Link | Next Follow-up Date | Follow-up Note | WhatsApp Link Output | Email Link Output | Scope of the Work | Quotation (INR) | Approved Quotation (INR) | WON (Yes/No) |
|-------------|-----|------------|--------------|----------------|----------|------------------|------------------|----------------|-------------|------------------|-------|----------|------|------|---------------|----------------------|----------------|----------------------|--------------------|--------------------|------------------|----------------------------|---------------|
| New | UIN001 | 2025-05-08 | CI4U Pvt Ltd | 9876543210 | Mumbai | [LinkedIn](#) | Attempted | Left voicemail | John Doe | 9876543210 | john@example.com | Awaiting response | 2025-05-08 | 10:00 AM | [Meet](#) | 2025-05-10 | Send intro PDF | [WhatsApp](#) | [Email](#) | Sensor Installation | 4500 | 4500 | Yes |
EOF

# Stage and push to GitHub
git add .
git commit -m "Initial commit: lead tracking table, CSV template, and sample data"
git push origin main
