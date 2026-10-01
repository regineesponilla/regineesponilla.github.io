# CASE STUDY #3: PROCESS IMPROVEMENT INITIATIVE

**Operational Efficiency & Data Quality Transformation**  
**Company:** Full Feeling Inc. (Dohtonbori, Philippines)  
**Role:** Digital Marketing & PR Officer  
**Timeline:** Mar 2024 – Jun 2024 (4 months, parallel to Dashboard project)  
**Status:** Completed | Results: 15 major process improvements implemented, 20% campaign ROI increase

---

## CONTEXT

While optimizing the dashboard, I discovered a deeper problem: the data feeding INTO the dashboard was itself broken. Reporting workflows, data collection procedures, and quality checks were fragmented across email, spreadsheets, manual entry points, and tribal knowledge.

Full Feeling Inc. had 6 branches generating data daily across:
- Point of sale transactions
- Inventory movements
- Staff scheduling and performance
- Customer engagement and marketing metrics
- Compliance and financial reporting

Each branch operated slightly differently. Data collection was inconsistent. Quality checks were sporadic. By the time data reached the central dashboard, it was often incomplete, late, or incorrect.

This became my secondary focus: identify the process inefficiencies preventing clean data from flowing into reporting systems, then design and implement fixes.

---

## THE PROBLEM

**20 Inefficient Processes Identified**

Through stakeholder interviews and process mapping, I documented 20 distinct reporting and data workflow problems:

### Data Collection Issues (7 processes)
1. Branch managers manually typed POS data into email forms (prone to transcription errors)
2. Inventory counts happened quarterly instead of continuously (creating stockouts and overstocking)
3. Daily sales figures took 3-4 hours to consolidate because they came in at different times from different branches
4. Customer feedback data was collected in spreadsheets instead of a centralized system
5. Marketing campaign performance was reported in multiple formats (some PDF, some Excel, some email)
6. Staff scheduling data was maintained in 3 different systems (payroll, scheduling app, and physical roster)
7. Non-financial data (foot traffic, customer satisfaction) was missing entirely from formal reporting

### Reporting Appearance & Structure Issues (5 processes)
8. Daily reports had inconsistent formatting (different branch managers used different templates)
9. Weekly reports mixed historical data with current data without clear date labeling
10. Monthly summaries lacked context (no prior-month or year-over-year comparisons)
11. Charts and visualizations were designed for print (not web), making them hard to interpret on screen
12. Executive dashboard didn't distinguish between "preliminary" and "final" data

### Data Quality & Missing Data Issues (8 processes)
13. No validation rules: negative revenue values, impossible quantities, future-dated transactions all slipped through
14. Missing data wasn't tracked or flagged; gaps would go unnoticed until end-of-month reconciliation
15. Duplicate transactions weren't being detected (same transaction reported by 2 branches)
16. Decimal places inconsistent (some reports rounded to whole numbers, others had cents)
17. No audit trail for data changes; couldn't tell if numbers were corrected or corrupted
18. Historical data lacked metadata (didn't know which system data came from, when it was last updated)
19. Branch-level anomalies weren't surfaced (one branch missing a day of data went unnoticed for 2 weeks)
20. No version control; multiple versions of "the truth" circulated (which month-end report was final?)

---

## THE PROCESS

### PHASE 1: PROCESS MAPPING & PRIORITIZATION

I mapped the entire data flow from collection to reporting:

**Current State:**
- Branch A files data → Email to finance → Manual consolidation → Excel calculation → Dashboard refresh

**Blockers identified:**
- Email delays (2-3 hour wait for all branches to submit)
- Manual consolidation (error-prone, time-consuming, inconsistent)
- No validation between branches
- No way to know which data was final vs preliminary

I prioritized by impact:
- **High impact:** Processes affecting multiple branches or causing major data quality issues
- **High feasibility:** Fixes that didn't require new tools or major system changes
- **Quick wins:** Improvements that could be done in 1-2 weeks

### PHASE 2: DESIGNING SOLUTIONS

I grouped the 20 processes into 5 solution categories:

**Solution 1: Standardized Data Collection Templates (Fixes 3 processes)**
- Replaced email forms and spreadsheets with a standardized daily submission template
- Built in validation: required fields, data type checks, reasonable value ranges
- Added branch identifier and timestamp to every record
- Result: Reduced data entry time by 30%, eliminated most transcription errors

**Solution 2: Data Quality Rules & Validation (Fixes 8 processes)**
- Created a "data quality checklist" that ran automatically on all incoming data
- Flagged: missing values, outliers (values more than 3 standard deviations from normal), impossible values (negative revenue, duplicate transactions)
- Set up error notifications so data issues were caught same-day instead of end-of-month
- Created an audit log tracking every data change
- Result: 47 data quality issues caught and corrected in the first month

**Solution 3: Reporting Standardization & Structure (Fixes 5 processes)**
- Redesigned all reports with consistent format, clear date labeling, and visual hierarchy
- Added "preliminary" vs "final" data markers
- Built prior-period comparisons into every report
- Redesigned charts for screen viewing (not print)
- Result: Stakeholders could now understand reports at a glance without asking for clarification

**Solution 4: Automated Data Consolidation (Fixes 3 processes)**
- Set up automated data pulls from branch systems instead of manual email submission
- Staggered pulls so all data arrived within 30 minutes (instead of 3-4 hours)
- Automated consolidation and reconciliation
- Result: Daily reports ready 2 hours earlier; zero manual consolidation errors

**Solution 5: Data Governance Documentation (Fixes 2 processes)**
- Created a data dictionary documenting each field, its source, and acceptable values
- Established clear ownership: who is responsible for each data source
- Published data refresh schedule: what data arrives when, which data is preliminary vs final
- Trained all stakeholders on data quality expectations
- Result: Clear "single source of truth" and no more version conflicts

---

### PHASE 3: IMPLEMENTATION & ROLLOUT

**Timeline:**
- Week 1-2: Designed templates and validation rules
- Week 3: Tested with Branch A (pilot)
- Week 4: Rolled out to all 6 branches with training
- Week 5-12: Monitored, refined, documented learnings

**Key Implementation Steps:**

1. **Pilot with Branch A:**
   - Used new templates for 2 weeks
   - Collected feedback: what worked, what was confusing
   - Adjusted templates based on their input

2. **Stakeholder Training:**
   - Conducted 30-minute training sessions for each branch
   - Showed how to use templates, what validation checks to expect, how to interpret error messages
   - Addressed concerns ("Will this take longer?" No, actually saves 45 minutes per week)

3. **Gradual Rollout:**
   - Launched new process on Monday morning
   - Provided 24/7 support for first week
   - Adjusted templates within first 3 days based on real usage

4. **Monitoring & Refinement:**
   - Tracked adoption rate, error rates, time savings
   - Made small tweaks based on feedback (e.g., one branch's POS system formatted time differently, updated template)
   - By week 4, all branches fully adopted

---

## OUTCOMES

### QUANTIFIED RESULTS

**Process Improvements Implemented:**
- **Solution 1 (Templates):** 3 processes improved
- **Solution 2 (Data Quality):** 8 processes improved
- **Solution 3 (Reporting Standards):** 5 processes improved
- **Solution 4 (Automation):** 3 processes improved
- **Solution 5 (Governance):** 2 processes improved
- **Total:** 15 major process improvements implemented

**Time Savings:**
- **Daily data consolidation:** 3-4 hours → 30 minutes (88% reduction)
- **Weekly reporting preparation:** 6 hours → 2 hours
- **Month-end reconciliation:** 16 hours → 4 hours (due to validation catching issues same-day)
- **Overall organization-wide savings:** ~30 hours/month

**Data Quality Improvement:**
- **Data validation issues caught:** 47 in first month, trending down to 3-4/month by month 4
- **Duplicate transactions:** Eliminated (automated detection + audit trail)
- **Missing data incidents:** 2 incidents caught same-day (previously took 1-2 weeks to notice)
- **Data quality score:** Baseline 62% → Final 94% (measured by percentage of records passing validation)

**Campaign ROI Improvement:**
- **Before:** Marketing reported campaign performance sporadically; ROI estimates were rough (±20% accuracy)
- **After:** Real-time campaign tracking by branch; ROI reported daily with ±5% accuracy
- **Result:** 20% increase in campaign ROI because marketing team could now see which campaigns worked and adjust quickly
  - Fixed underperforming campaigns within 3 days instead of 2 weeks
  - Reallocated budget to high-performing campaigns faster
  - Tested new campaigns with faster feedback loops

### Business Impact

**Executive Decision-Making:**
- Executives could now trust the data enough to make decisions based on it
- Previously, there was always a "but we should verify this" hesitation
- Now: data is trustworthy, decisions are faster

**Branch Manager Autonomy:**
- Managers could see their own performance in real-time
- Previously: had to wait for central reports to know their numbers
- Now: dashboards show live performance; managers can take corrective action same-day

**Finance & Compliance:**
- Month-end close time reduced from 8 days to 3 days (no more reconciliation battles)
- Audit trail satisfied compliance requirements (regulators could see data provenance)
- Fewer surprises during financial reviews

---

## LEARNINGS & REFLECTION

### What I Learned

**1. Process problems are often data problems**
- I thought the business processes were fine; the problem was just the dashboard performance
- Digging deeper revealed the processes themselves were broken
- **Lesson:** When data quality is bad, look at the processes generating the data, not the dashboard displaying it

**2. Validation rules beat manual quality checks**
- Previously, someone manually checked for obvious errors (but missed 90% of problems)
- Automated validation caught issues consistently
- **Lesson:** Automate what can be automated; save humans for judgment calls

**3. Standards matter**
- Once templates and standards existed, quality improved dramatically
- Before standards: every branch had their own way, leading to inconsistencies
- **Lesson:** Boring stuff (naming conventions, format standards) has huge impact

**4. Training changes adoption**
- I was worried about resistance to new processes
- When people understood WHY (faster reporting, better decisions for them), adoption was enthusiastic
- **Lesson:** Explain the benefit, not just the requirement

### What I'd Do Differently

**1. Start with process mapping earlier**
- I only discovered these issues because the dashboard project forced me to look at data quality
- Should have done a full process audit from day 1

**2. Involve branch managers as co-designers**
- The improvements I designed worked well, but branch-specific tweaks came from their feedback
- Should have had them in the design phase instead of just the implementation phase

**3. Measure pre-existing baseline metrics**
- I estimated "3-4 hours for consolidation" based on what people told me
- Should have actually timed it for a week before changes to have true before/after numbers

---

## CONCLUSION

This project proved that **fixing processes fixes everything downstream.**

By standardizing data collection, building in quality validation, automating consolidation, and establishing clear data governance, we transformed reporting from a painful daily ritual into a reliable tool that executives could trust and act on.

The 15 process improvements cascaded: faster reporting → better decision-making → higher campaign ROI → better business results. All from fixing how data flowed through the organization.

---

**Business Analyst Skills Demonstrated:**
- Process mapping and workflow analysis
- Problem identification and root cause analysis
- Solution design for operational efficiency
- Data quality and governance implementation
- Change management and stakeholder adoption
- Quantitative measurement of process improvements
- Training and documentation
