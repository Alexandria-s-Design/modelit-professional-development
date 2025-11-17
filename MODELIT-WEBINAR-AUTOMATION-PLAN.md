# ModelIt Professional Development Webinar Automation Plan
## Complete Make.com Strategy for "Getting Started" Webinar

**Launch Timeline**: 30 days
**Target Attendees**: 50-100 educators
**Cost**: $0 (100% free tools)
**Primary Goals**: Lead generation + Community building

---

## 🎯 AUTOMATION ARCHITECTURE

### **The Complete Funnel (5 Scenarios)**

```
Registration → Confirmation → Reminders → Webinar → Follow-up → Community
     ↓            ↓             ↓           ↓          ↓            ↓
  Make.com    Make.com      Make.com    Zoom     Make.com     Facebook
```

---

## 📋 SCENARIO 1: WEBINAR REGISTRATION WORKFLOW

**Trigger**: Google Form submission
**Tools**: Google Forms → Make.com → Gmail → Google Sheets → Calendly

### **Automation Flow**:
1. Teacher fills out registration form (Google Forms)
2. Make.com watches for new responses
3. Add registrant to Google Sheets master list
4. Send welcome email with:
   - Personal greeting
   - Calendly link to book their spot
   - Pre-webinar prep materials
   - Facebook Group invite link
5. Tag as "Webinar Registrant" in Google Sheets

### **Google Form Fields**:
- Full Name
- Email Address
- School Name
- Grade Level (K-5, 6-8, 9-12)
- Subject Area (Science, Health, Other)
- Experience with systems thinking (Beginner, Intermediate, Advanced)
- What do you hope to learn? (open text)

### **Make.com Scenario Structure**:
```
[Google Forms: Watch Responses]
    ↓
[Google Sheets: Add Row] → Master List
    ↓
[Router]
    ↓
    ├→ [Gmail: Send Email] → Welcome + Calendly link
    ├→ [Google Sheets: Update Row] → Tag "Registered"
    └→ [Airtable/Sheets: Add to Nurture Sequence]
```

**Free Tool**: Google Forms (unlimited forms)

---

## 📋 SCENARIO 2: AUTOMATED EMAIL SEQUENCE

**Trigger**: Time-based (scheduled)
**Tools**: Google Sheets → Make.com → Gmail

### **Email Sequence Timeline**:

**Email 1: Welcome (Immediate)**
- Subject: "You're Registered! Here's What to Expect 🎓"
- Content: Webinar overview, Calendly booking link, prep materials
- CTA: Add to calendar + Join Facebook Group

**Email 2: Prep Guide (7 days before)**
- Subject: "One Week Away! Quick Prep for ModelIt Success 🚀"
- Content: What to have ready, tech check instructions, preview video
- CTA: Reply with questions

**Email 3: 24-Hour Reminder**
- Subject: "Tomorrow: Getting Started with ModelIt! (Plus Zoom Link)"
- Content: Zoom link, final reminders, what to bring
- CTA: Click Zoom link to test audio/video

**Email 4: 1-Hour Reminder**
- Subject: "Starting in 1 Hour! See You Soon 🎉"
- Content: Zoom link, last-minute tips
- CTA: Join now

**Email 5: Post-Webinar Thank You (1 hour after)**
- Subject: "Thank You for Joining! Here Are Your Resources 📚"
- Content: Recording link, slides PDF, certificate, next steps
- CTA: Join Facebook Group + Rate the webinar

**Email 6: Nurture Sequence (3 days after)**
- Subject: "Ready to Go Deeper with ModelIt?"
- Content: Next webinar dates, TPT resources, pilot program info
- CTA: Book 1:1 consultation OR Join pilot program

**Email 7: Case Study (7 days after)**
- Subject: "How Mrs. Johnson Used ModelIt to Transform Her Classroom"
- Content: Teacher success story, student outcomes
- CTA: Share your story + Get featured

### **Make.com Scenario Structure**:
```
[Schedule: Daily at 9am ET]
    ↓
[Google Sheets: Search Rows] → Find teachers needing emails today
    ↓
[Iterator] → Loop through each teacher
    ↓
[Router] → Check which email they need
    ↓
    ├→ Email 1 (Day 0)
    ├→ Email 2 (Day -7)
    ├→ Email 3 (Day -1)
    ├→ Email 4 (Hour -1)
    ├→ Email 5 (Hour +1)
    ├→ Email 6 (Day +3)
    └→ Email 7 (Day +7)
    ↓
[Google Sheets: Update Row] → Mark email sent
```

**Free Tool**: Gmail (500 emails/day limit with free account)

---

## 📋 SCENARIO 3: FACEBOOK GROUP AUTOMATION

**Trigger**: Post-webinar completion
**Tools**: Google Sheets → Make.com → Facebook Groups API

### **Automation Flow**:
1. After webinar ends (Zoom webhook OR manual Google Sheet update)
2. Make.com checks Google Sheets for attendees
3. Send personalized Facebook Group invite via Gmail
4. Post welcome message in group tagging new members
5. Send weekly discussion prompts to keep group active

### **Facebook Group Structure**:
- **Name**: "ModelIt! K12 Teacher Community"
- **Description**: Exclusive community for educators using ModelIt and Cell Collective
- **Sections**:
  - 📚 Getting Started Resources
  - 💬 Teacher Q&A
  - 🎓 Success Stories
  - 📅 Upcoming Webinars
  - 🎁 Exclusive TPT Discounts

### **Weekly Engagement Posts (Automated)**:
- Monday: Tip of the Week
- Wednesday: Teacher Spotlight
- Friday: Challenge of the Week

### **Make.com Scenario Structure**:
```
[Google Sheets: Watch Rows] → New attendee marked "Completed"
    ↓
[Gmail: Send Email] → Facebook Group invite with personal note
    ↓
[Delay: 2 hours]
    ↓
[HTTP: Facebook Graph API] → Post welcome message in group
    ↓
[Google Sheets: Update Row] → Mark "Invited to Community"
```

**Free Tool**: Facebook Groups (unlimited members)

---

## 📋 SCENARIO 4: LEAD NURTURE & SALES FUNNEL

**Trigger**: Webinar completion
**Tools**: Google Sheets → Make.com → Gmail

### **Lead Scoring System** (Google Sheets):
- Registered: +10 points
- Attended: +25 points
- Joined Facebook Group: +15 points
- Downloaded resources: +10 points
- Opened 3+ emails: +20 points
- **HOT LEAD**: 60+ points = Ready for pilot program

### **Automated Actions by Score**:

**0-30 points (Cold)**:
- Weekly newsletter with tips
- Occasional webinar reminders

**31-59 points (Warm)**:
- Bi-weekly case studies
- TPT discount codes
- Invite to next webinar

**60+ points (Hot)**:
- Personal email from you
- 1:1 consultation offer
- Pilot program invitation
- Priority support access

### **Make.com Scenario Structure**:
```
[Schedule: Daily at 10am ET]
    ↓
[Google Sheets: Search Rows] → Calculate lead scores
    ↓
[Iterator] → Loop through each lead
    ↓
[Router] → Check score range
    ↓
    ├→ [Cold Leads: Weekly Newsletter]
    ├→ [Warm Leads: Case Study + Discount]
    └→ [Hot Leads: Personal Outreach + Pilot Invite]
    ↓
[Google Sheets: Update Row] → Update score & last contact date
```

**Free Tool**: Google Sheets (unlimited rows for lead tracking)

---

## 📋 SCENARIO 5: COMPLETION CERTIFICATE GENERATOR

**Trigger**: Webinar attendance confirmed
**Tools**: Google Sheets → Make.com → Google Slides API → Gmail

### **Automation Flow**:
1. Teacher attends webinar (marked in Google Sheets)
2. Make.com triggers certificate generation
3. Google Slides template auto-populates:
   - Teacher name
   - Date of completion
   - Webinar title
   - 1.5 PD hours credit
4. Export as PDF
5. Email certificate with thank you message

### **Certificate Template Fields** (Google Slides):
- `{{TEACHER_NAME}}`
- `{{DATE}}`
- `{{WEBINAR_TITLE}}`
- `{{PD_HOURS}}`
- Signature: Dr. Marie Martin, ModelIt! K12

### **Make.com Scenario Structure**:
```
[Google Sheets: Watch Rows] → "Attended" = YES
    ↓
[Google Slides: Copy Presentation] → Duplicate template
    ↓
[Google Slides: Replace Text] → Insert teacher name, date, etc.
    ↓
[Google Drive: Export as PDF]
    ↓
[Gmail: Send Email] → Attach certificate PDF
    ↓
[Google Sheets: Update Row] → Mark "Certificate Sent"
```

**Free Tool**: Google Slides (unlimited presentations)

---

## 🎨 CONTENT CREATION PLAN

### **Webinar: "Getting Started with ModelIt!"**
**Duration**: 60 minutes (45 min presentation + 15 min Q&A)

### **Outline**:
1. **Welcome & Introductions** (5 min)
   - Who we are
   - Poll: What's your biggest challenge teaching systems thinking?

2. **What is ModelIt?** (10 min)
   - Cell Collective platform overview
   - Boolean modeling for kids
   - NGSS alignment (MS-LS1, MS-LS2, HS-LS1)

3. **Live Demo: Immune System Model** (15 min)
   - Screen share Cell Collective
   - Build simple T-cell activation model
   - Show how students interact

4. **Classroom Integration** (10 min)
   - Lesson plan walkthrough
   - Google Classroom setup
   - Student accounts & management

5. **Success Stories** (5 min)
   - Teacher testimonials
   - Student work examples
   - Before/after assessment data

6. **Resources & Next Steps** (5 min)
   - Free TPT resources
   - Next webinar dates
   - Pilot program opportunity

7. **Q&A** (15 min)

### **Slide Deck** (30 slides):
- Title slide with branding
- Agenda
- 20 content slides
- 5 demo screenshots
- 3 testimonial slides
- Resources slide
- Call-to-action slide

### **Handouts** (PDF):
1. **Quick Start Guide** (2 pages)
   - Account setup steps
   - First model walkthrough
   - Troubleshooting tips

2. **NGSS Alignment Chart** (1 page)
   - Standards mapped to Cell Collective models
   - Grade level recommendations

3. **Lesson Plan Template** (3 pages)
   - 5E format (Engage, Explore, Explain, Elaborate, Evaluate)
   - Pre-filled immune system example
   - Editable for other topics

---

## 📊 MASTER TRACKING SPREADSHEET

### **Google Sheets: "ModelIt Webinar CRM"**

**Tabs**:
1. **Registrants** - All sign-ups
2. **Attendees** - Who showed up
3. **Email Tracking** - Which emails sent when
4. **Lead Scores** - Calculated scores + status
5. **Certificates** - Issued certificates log
6. **Facebook Members** - Community join dates
7. **Analytics** - Conversion rates, engagement metrics

**Key Columns** (Registrants tab):
- Timestamp
- Full Name
- Email
- School
- Grade Level
- Subject
- Experience Level
- Registration Date
- Calendly Booked (Y/N)
- Attended (Y/N)
- Certificate Sent (Y/N)
- Facebook Member (Y/N)
- Lead Score (calculated)
- Status (Cold/Warm/Hot)
- Last Contact Date
- Notes

**Formulas for Lead Scoring**:
```
=IF(H2="Y", 10, 0) + IF(I2="Y", 25, 0) + IF(J2="Y", 15, 0) + IF(K2="Y", 15, 0)
```

---

## 🚀 30-DAY IMPLEMENTATION TIMELINE

### **Week 1: Foundation Setup** (Days 1-7)
- [ ] Create Google Forms registration form
- [ ] Set up Google Sheets master tracking spreadsheet
- [ ] Create Facebook Group "ModelIt! K12 Teacher Community"
- [ ] Set up Calendly for webinar booking
- [ ] Design email templates (7 emails)
- [ ] Create Google Slides certificate template

### **Week 2: Make.com Scenarios** (Days 8-14)
- [ ] Build Scenario 1: Registration workflow
- [ ] Build Scenario 2: Email sequence
- [ ] Build Scenario 3: Facebook Group automation
- [ ] Build Scenario 4: Lead nurture funnel
- [ ] Build Scenario 5: Certificate generator
- [ ] Test all scenarios with dummy data

### **Week 3: Content Creation** (Days 15-21)
- [ ] Create webinar slide deck (30 slides)
- [ ] Record demo video (Cell Collective walkthrough)
- [ ] Write handouts (Quick Start Guide, NGSS Chart, Lesson Plan)
- [ ] Design social media graphics for promotion
- [ ] Write Facebook Group welcome post
- [ ] Create weekly engagement posts (12 weeks)

### **Week 4: Launch & Promotion** (Days 22-30)
- [ ] Publish registration form on ModelIt website
- [ ] Share in Facebook education groups (20+ groups)
- [ ] Email existing contact list
- [ ] Post on LinkedIn, Twitter, Instagram
- [ ] Reach out to teacher influencers (10 contacts)
- [ ] Monitor registrations and test automation
- [ ] Host webinar!
- [ ] Send follow-up emails and certificates
- [ ] Welcome new Facebook Group members

---

## 🔧 MAKE.COM SCENARIO BLUEPRINTS

### **Scenario 1: Registration Workflow**

**Modules Needed**:
1. Google Forms: Watch Responses
2. Google Sheets: Add a Row (Master List)
3. Tools: Set Variable (store name, email)
4. Gmail: Send an Email
5. Google Sheets: Update a Row (mark "Registered")

**Operations Per Month**: ~200 (100 registrants × 2 operations each)
**Make.com Free Tier**: 1,000 operations/month ✅

---

### **Scenario 2: Email Sequence**

**Modules Needed**:
1. Tools: Schedule (daily at 9am)
2. Google Sheets: Search Rows (find teachers needing emails)
3. Iterator (loop through results)
4. Router (7 routes - one per email)
5. Gmail: Send an Email (×7)
6. Google Sheets: Update a Row (mark sent)

**Operations Per Month**: ~700 (100 teachers × 7 emails)
**Make.com Free Tier**: 1,000 operations/month ✅

---

### **Scenario 3: Facebook Group Invite**

**Modules Needed**:
1. Google Sheets: Watch Rows (new attendee)
2. Gmail: Send an Email (Facebook invite)
3. Tools: Sleep (delay 2 hours)
4. HTTP: Make a Request (Facebook Graph API - optional)
5. Google Sheets: Update a Row (mark invited)

**Operations Per Month**: ~300 (75 attendees × 4 operations)
**Make.com Free Tier**: 1,000 operations/month ✅

---

### **Scenario 4: Lead Scoring**

**Modules Needed**:
1. Tools: Schedule (daily at 10am)
2. Google Sheets: Search Rows (all leads)
3. Iterator (loop through leads)
4. Tools: Set Variable (calculate score)
5. Router (3 routes: Cold/Warm/Hot)
6. Gmail: Send an Email
7. Google Sheets: Update a Row (update score)

**Operations Per Month**: ~600 (100 leads × 6 operations)
**Make.com Free Tier**: 1,000 operations/month ✅

---

### **Scenario 5: Certificate Generator**

**Modules Needed**:
1. Google Sheets: Watch Rows (attended = YES)
2. Google Slides: Copy a Presentation
3. Google Slides: Replace Text in Presentation (×4 fields)
4. Google Drive: Download a File (export PDF)
5. Gmail: Send an Email (attach PDF)
6. Google Sheets: Update a Row (mark sent)

**Operations Per Month**: ~450 (75 attendees × 6 operations)
**Make.com Free Tier**: 1,000 operations/month ✅

---

## 💰 TOTAL COST ANALYSIS

| Tool | Cost | Purpose |
|------|------|---------|
| Google Forms | FREE | Registration |
| Google Sheets | FREE | CRM & tracking |
| Gmail | FREE | All emails (500/day limit) |
| Calendly | FREE | Scheduling (1 event type) |
| Zoom | FREE | Webinar (100 participants, 40 min limit) |
| Google Slides | FREE | Certificates |
| Facebook Groups | FREE | Community |
| Make.com | FREE | Automation (1,000 ops/month) |

**Total Monthly Cost**: $0

**Upgrade Recommendations** (Optional):
- Zoom Pro: $15/month (unlimited time, 100 participants)
- Make.com Core: $9/month (10,000 operations)

---

## 📈 SUCCESS METRICS

### **Track These KPIs**:
1. **Registration Rate**: Goal 100 registrants in 30 days
2. **Attendance Rate**: Goal 75% (75 attendees)
3. **Email Open Rate**: Goal 40%+
4. **Facebook Group Join Rate**: Goal 50% (50 members)
5. **Hot Lead Conversion**: Goal 10 pilot program signups

### **Google Sheets Formulas** (Analytics tab):
```
Attendance Rate: =COUNTIF(Attendees!I:I,"Y")/COUNTA(Registrants!A:A)
Email Open Rate: (Track with Gmail read receipts - manual)
FB Join Rate: =COUNTIF(Registrants!K:K,"Y")/COUNTA(Registrants!A:A)
Hot Leads: =COUNTIF('Lead Scores'!N:N,"Hot")
```

---

## 🎯 NEXT STEPS

**Priority 1: Foundation** (Do This Week)
1. Create Google Forms registration form
2. Set up Google Sheets tracking spreadsheet
3. Create Facebook Group

**Priority 2: Automation** (Week 2)
4. Build Make.com Scenario 1 (Registration)
5. Test with your own email

**Priority 3: Content** (Week 3)
6. Create slide deck outline
7. Write email templates

**Want me to build any of these scenarios RIGHT NOW?** I can:
- Create the Google Form
- Build the Make.com scenarios
- Write all 7 email templates
- Design the certificate template
- Generate the webinar slide deck

Just tell me what you want to tackle first! 🚀
