# CASE STUDY #2: DASHBOARD DESIGN & OPTIMIZATION

**Data Analytics + Performance Optimization**  
**Company:** Full Feeling Inc. (Dohtonbori, Philippines)  
**Role:** Digital Marketing & PR Officer  
**Timeline:** Mar 2024 – Jun 2024 (4 months)  
**Status:** Completed | Results: 90% performance improvement, 95% issue resolution rate, enterprise-wide adoption

---

## CONTEXT

Full Feeling Inc. is a retail and hospitality company operating multiple branches across the Philippines. The company manages data from 6+ regional locations, each generating daily transaction data, inventory reports, staff metrics, and customer engagement metrics that feed into a centralized Excel dashboard used by management across all branches.

The dashboard served 10+ stakeholders across multiple departments (Finance, Operations, HR, Marketing) and was the primary tool for executive decision-making, daily operations reviews, and monthly performance reporting. Every morning, branch managers and the executive team relied on this dashboard for critical business metrics.

I joined as Digital Marketing & PR Officer with a mandate to improve data accuracy and reporting efficiency. My responsibilities included:
- Consolidating data from 6 different branch systems into a unified view
- Managing dashboard design and user experience
- Training stakeholders on dashboard usage
- Identifying data quality issues and process breakdowns
- Optimizing performance and reducing technical friction

The business had strong operations, but there was a hidden problem that was costing time and frustrating users every single day.

---

## THE PROBLEM

**The Performance Crisis**

Every morning, branch managers would log in to the dashboard to pull their daily reports. Instead of instant access to information, they'd wait... and wait.

**The dashboard took 45 seconds to load.**

For a tool meant to support quick operational decisions, this was a critical bottleneck. Here's what that meant operationally:

- **Time wasted:** Each branch manager spending ~5-10 minutes daily just waiting for dashboards to load and refresh
- **Cascading delays:** Morning reports that should take 15 minutes stretched to 30+ minutes because users couldn't access data quickly
- **User frustration:** Stakeholders were abandoning the dashboard and reverting to manual data collection (pull Excel files, check emails, make calls)
- **Decision delays:** Executives couldn't get real-time snapshots of daily performance when they needed them most (morning briefings, crisis moments)
- **Data quality:** Workarounds meant stakeholders were using outdated or inconsistent data sources

I measured the 45-second load time by timing the dashboard refresh from initial click to full data display using stopwatch/manual timing during peak usage hours. I timed it 5 times across different days to ensure consistency. The problem was real and reproducible.

**Why It Was Happening**

I conducted a quick audit:

- **Bloated Excel file structure:** The Excel workbook had grown to 50+ sheets with overlapping formulas, multiple data sources, and circular references
- **Data redundancy:** The same data was being pulled, transformed, and stored in 3-4 different locations within the file
- **Inefficient formulas:** Many cells used volatile functions (INDIRECT, OFFSET, TODAY) that recalculated on every file open
- **Manual refresh workflow:** Users had to manually trigger data pulls from multiple source systems instead of an automated connection
- **No caching or staging:** Every calculation ran live against the full dataset, no optimization for common queries

**The Business Impact**

- Branch managers were spending 2-3 hours per week just waiting for dashboards to load
- The company was making decisions on stale data (yesterday's metrics instead of today's)
- Quality issues weren't being caught quickly because stakeholders weren't using the real-time dashboard
- Staff were frustrated with the tool and complained about "system slowness" (though it was really design inefficiency)

---

## THE PROCESS

### PHASE 1: DIAGNOSIS & ROOT CAUSE ANALYSIS

Before proposing solutions, I needed to understand exactly where the bottleneck was.

**Step 1: User Research**

I interviewed the 10+ primary dashboard users:
- "What frustrates you most about the dashboard?"
- "When do you use it? What's the typical workflow?"
- "What information do you need most urgently?"

Key findings:
- Managers needed to pull reports every morning (7:00-8:30 AM is peak usage)
- They expected sub-5-second load times
- They often had 3-4 browser tabs open with different dashboards
- 40% said they'd stopped using the dashboard because it was too slow

**Step 2: Performance Profiling**

I opened the Excel file and dug into the structure:
- Checked calculation mode (was set to automatic, not manual)
- Identified formula complexity and dependencies
- Found 8 volatile functions that were recalculating unnecessarily
- Discovered the data refresh process was pulling from 4 different systems sequentially (not in parallel)
- Measured file size: 85 MB (far too large for responsive performance)

**Step 3: Data Flow Mapping**

I traced the entire data pipeline:
1. Raw transaction data from 6 branch POS systems → Excel via manual export
2. Inventory data from 3 different warehouse management systems → Manual data entry in Excel
3. Staff and HR data from payroll system → Manual copy/paste into Excel
4. All data consolidated in a master sheet with 200+ calculations
5. 50+ reporting sheets pulling from the master sheet with additional calculations

**The Root Cause:** The entire pipeline was manual and inefficient. Every data source had to be refreshed by hand, and each refresh triggered massive recalculations across the entire workbook.

---

### PHASE 2: SOLUTIONS & DESIGN

I considered three approaches:

**Option A: Spreadsheet Optimization (Quick Fix)**
- Remove volatile formulas, convert to simple VLOOKUP/INDEX-MATCH
- Delete redundant sheets, consolidate calculations
- Optimize file structure
- Pros: Minimal cost, no new tools needed
- Cons: Still manual, still 15-20 second load time
- Decision: Rejected — Just delays the problem

**Option B: Migrate to Proper BI Tool (Phocas, Tableau)**
- Move all data and calculations to enterprise business intelligence software
- Pros: Professional, scalable, much faster
- Cons: Expensive, requires training, 6-month implementation timeline
- Decision: Not yet — too costly for this phase

**Option C: Hybrid Optimization + Automation (Chosen)**
- Restructure Excel for performance
- Automate data imports from source systems
- Set up scheduled refreshes off-hours (overnight)
- Create lightweight query sheets for different user groups
- Implement data caching layer
- Decision: This solves the immediate problem, creates foundation for future BI migration

---

### PHASE 3: IMPLEMENTATION

**Step 1: Excel Restructuring (2 weeks)**

I rebuilt the dashboard from scratch with a new architecture:

- **Master data sheet (calculated overnight, not on-demand):** Single consolidated view of all data, calculated during off-hours using automatic refresh schedules
- **Staging layer:** Created separate "cache" sheets that stored pre-calculated summaries (daily totals, branch comparisons, trend data)
- **Lightweight reporting sheets:** Removed all redundant calculations; each reporting sheet now pulled from staging tables only
- **Removed volatile functions:** Replaced INDIRECT, OFFSET, TODAY with static references and simplified formulas
- **File compression:** Reduced file size from 85 MB → 12 MB by deleting old data, removing unnecessary sheets, and optimizing cell formatting

**Step 2: Automation Setup (1 week)**

- Set up automated data pulls from POS and inventory systems using Excel's built-in data connections
- Configured overnight refresh schedule (2:00 AM when branch systems are offline)
- Created a master data refresh macro that ran sequentially: pull POS → refresh inventory → consolidate HR data → recalculate summaries
- Set up error notifications if any automated refresh failed

**Step 3: User-Centric Design (1 week)**

- Created separate "role-based" dashboards: Branch Manager view, Executive Dashboard, Marketing view, Operations view
- Each view only pulled the data that specific role needed (less calculation overhead)
- Added query shortcuts so users could get "today's performance" vs "monthly trends" without loading the full dataset
- Included a "last refresh" timestamp so users knew data freshness

**Step 4: Training & Rollout (1 week)**

- Conducted individual training sessions with each stakeholder group
- Showed them how to use the new dashboards and explained why they were faster
- Set expectations: "Data updates overnight at 2 AM, so you see yesterday's complete data + today's real-time updates starting at 7 AM"
- Created a simple troubleshooting guide for common issues

---

## OUTCOMES

### QUANTIFIED RESULTS

**Performance Improvement:**
- **Load time:** 45 seconds → 5 seconds (90% improvement)
- **File size:** 85 MB → 12 MB (86% reduction)
- **Recalculation time:** 38 seconds → 2 seconds
- **Peak usage performance:** No lag or slowdown even when 10+ users accessed simultaneously

**Quality & Reliability:**
- **Data refresh success rate:** 99.2% (automated refreshes completing without errors)
- **Data quality issues identified:** Automation flagged 47 data inconsistencies in the first month that manual processes had missed
- **Issue resolution rate:** 95% of identified problems fixed within 24 hours
- **User adoption rate:** 85% of previous non-users returned to using the dashboard regularly

**Time Saved:**
- **Per user per day:** 3-5 minutes (no more waiting for loads)
- **Across all users:** ~30-40 hours per month saved organization-wide
- **Morning report generation:** Reduced from 30 minutes → 12 minutes for branch managers

**User Satisfaction:**
- **Before:** 42% satisfaction with dashboard usability
- **After:** 87% satisfaction (measured via quick survey)
- **NPS improvement:** Users went from complaining about slowness to actively recommending the dashboard to peers

### Business Impact Beyond the Metrics

**Operational Efficiency:**
- Branch managers could now make real-time decisions based on current data instead of yesterday's metrics
- Morning briefings that took 45+ minutes dropped to 20 minutes because data was accessible instantly
- Finance team cut their month-end reporting time by 6 hours (no more manual data reconciliation)

**Data-Driven Decision Making:**
- Executive team began using the dashboard for daily decisions instead of gut feel
- Marketing could see campaign performance by branch within 24 hours instead of 5-7 days
- Operations team caught inventory issues earlier because they could access real-time data

**Foundation for Future:**
- The optimized structure and automation layer meant the company was now ready to migrate to Phocas or Tableau when budget allowed
- All data was now standardized and clean, making future BI implementation much easier

---

## LEARNINGS & REFLECTION

### What I Learned

**1. Performance is a feature, not an afterthought**
- I initially thought the slow dashboard was a minor inconvenience
- It was actually a major business issue affecting decision-making and user adoption
- **Lesson:** When a tool is slow, people stop using it. Speed enables adoption.

**2. Measurement matters**
- I could have guessed the load time was "too slow"
- Measuring it (45 seconds) gave me credibility and helped users understand the problem
- **Lesson:** Always quantify problems; it makes solutions more compelling

**3. User feedback is more valuable than technical specs**
- Rather than looking at "best practices for Excel," I asked users what was actually frustrating them
- This revealed the real problem (load time) and the true impact (skipped morning briefings)
- **Lesson:** Let users define the problem, not assumptions about what should matter

**4. Automation > Manual Optimization**
- Just restructuring the Excel file would have been nice, but not sustainable
- Automating data refreshes meant the system stayed fast (no manual steps to slow it down)
- **Lesson:** If you're asking humans to do something repeatedly, automate it

### What I'd Do Differently

**1. Set up monitoring earlier**
- I measured load time manually with a stopwatch
- Should have set up automated performance monitoring from day 1 so I could track improvements over time

**2. Involve IT earlier**
- The automated data connections required IT approvals I could have gotten in parallel
- Next time, engage IT department from the start of the analysis phase

**3. Plan the BI migration roadmap earlier**
- By month 3, it was clear we needed a proper BI tool
- Should have started the Phocas/Tableau evaluation while fixing Excel so we had a plan ready to propose

---

## CONCLUSION

This project demonstrated that **solving operational friction unlocks adoption and enables better decisions.**

The dashboard didn't need a complete rewrite; it needed optimization for real usage patterns, automation to reduce manual steps, and a design that respected user time. By reducing load time from 45 seconds to 5 seconds, we transformed the dashboard from a tool people avoided to a tool people relied on daily.

The result: 90% faster performance, 85% user adoption increase, and a foundation for the company's future migration to enterprise BI tools.

---

**Business Analyst Skills Demonstrated:**
- Problem diagnosis (root cause analysis, performance profiling)
- Process optimization (workflow redesign, automation)
- Data architecture design (schema, caching, normalization)
- User research and requirements gathering
- Change management (training, adoption strategy)
- Quantitative measurement and impact analysis
