flowchart LR

%% =========================================================
%% R1 / FIND THE SIX RELICS
%% HR RECRUITING
%% =========================================================

subgraph HT["HIRING TEAM / INTERVIEWERS"]

    B1["<b>B1 Hiring Request Intake</b><br/>
    <i>Email · approval memo</i><br/><br/>
    1. Managers request by email & form - missing fields bounce back<br/>
    2. Hiring memo in a 3-tier sign-off queue - single-digit rejection rate<br/>
    3. Register the position in the system<br/>
    4. Reply with a confirmation email"]

    B9["<b>B9 Panel Interview</b><br/><br/>
    1. Skim the résumé minutes before - question prep is everyone's own problem<br/>
    2. Team-fit call inside the conversation - 'this person, every day?'<br/>
    3. The conversation isn't recorded - scorecards written later, from memory"]

    B10["<b>B10 Executive Interview</b><br/><br/>
    1. Compile round-1 results & comments in Excel<br/>
    2. Write the executive summary deck<br/>
    3. Two weeks waiting on executive calendars - the candidate signs elsewhere<br/>
    4. The final hiring decision"]

end


subgraph REC1["RECRUITING — Sourcing & coordination"]

    B2["<b>B2 Draft the JD</b><br/>
    <i>Recruiting system · Word</i><br/><br/>
    1. Find a 3-year-old JD and copy it - swap the company blurb, reuse the rest<br/>
    2. Email the hiring team for review > wait > revise; 2-3 round trips<br/>
    3. Version control by filename: vF, vF2, real_final.docx"]

    B3["<b>B3 Market Benchmark Check</b><br/>
    <i>Job portals · Excel</i><br/><br/>
    1. Search job portals for 10-15 similar postings<br/>
    2. Compile the collected pay & requirements into Excel<br/>
    3. Compare against the once-a-year salary-survey snapshot<br/>
    4. 'Can we hire at these terms?' - the team lead's gut call"]

    B4["<b>B4 Post the Job</b><br/>
    <i>4 job portals</i><br/><br/>
    1. Reformat the final JD for each portal's template and character limits<br/>
    2. Log in to four job portals, one by one, and post<br/>
    3. Post, then wait for inbound - candidates picked only from who applies"]

    B5["<b>B5 Collect & Sort Applications</b><br/>
    <i>Portal admin pages</i><br/><br/>
    1. Download from each platform's admin page, upload into the recruiting system<br/>
    2. De-duplicate by matching names and emails, by eye<br/>
    3. Arrivals pile up in a queue - screened once a week, Friday afternoon<br/>
    4. Past-applicant & reject pool stays closed - only fresh arrivals count"]

    B8["<b>B8 Interview Scheduling</b><br/>
    <i>Email · calendar</i><br/><br/>
    1. Hunt for free slots across calendars - executives via their assistants<br/>
    2. Email the candidate for availability > wait days > reschedule ping-pong<br/>
    3. After confirming: calendar invites, room booking, info emails"]

end


subgraph REC2["RECRUITING — Screening & offer"]

    B6["<b>B6 Screening & Deep Review</b><br/><br/>
    1. Check must-have qualifications by hand, item by item<br/>
    2. Verify tenure, employers, and titles on the résumé<br/>
    3. Read job-hopping & gaps - 'minus if they move every 2 years', each screener's gut<br/>
    4. Score the match between experience and JD requirements<br/>
    5. Open portfolio & GitHub links - top few only, for lack of time<br/>
    6. Infer motivation & culture fit from essays - every reviewer, a different bar"]

    B11["<b>B11 Reference Check</b><br/><br/>
    1. Call the listed references - wait days when nobody picks up<br/>
    2. Run the reference interview on the standard questionnaire<br/>
    3. Hand-write the reference summary report<br/>
    4. Cross-check statements against interview impressions - the checker's hunch"]

    B12["<b>B12 Comp Design & Offer Negotiation</b><br/>
    <i>Salary tables · Excel</i><br/><br/>
    1. Look up salary tables, hand-check equity against the current team<br/>
    2. Exactly three comp scenarios drafted - min / target / max<br/>
    3. Submit the package to the comp committee and wait - revisions almost never happen<br/>
    4. Persuade the candidate, negotiate to agreement - calls and meetings<br/>
    5. Redraft the formal offer letter from the agreed terms<br/>
    6. Send the letter, track the e-signature"]

end


subgraph OPS["HR OPS / IT — Setup & onboarding"]

    B13["<b>B13 Paperwork & System Setup</b><br/>
    <i>Email · HRIS</i><br/><br/>
    1. Email the document checklist, chase gaps with individual reminders<br/>
    2. Re-type information from the application into the HR system"]

    B14["<b>B14 Onboarding Prep</b><br/><br/>
    1. Email IT for equipment, file separate tickets for accounts<br/>
    2. Readiness checked only the day before - gaps surface on morning one"]

    B15["<b>B15 Day-One Welcome</b><br/><br/>
    1. Team welcome & psychological safety<br/>
    2. Staff answer the same policy/facility/system questions, over and over<br/>
    3. Culture & unwritten norms - things you learn by asking a senior"]

end


%% =========================================================
%% MAIN PROCESS FLOW
%% =========================================================

B1 -->|"Approved - handed over"| B2

B2 --> B3
B3 --> B4
B4 --> B5

B5 -->|"Friday screening queue"| B6

B6 -->|"Interview shortlist"| B8

B8 -->|"Schedule set"| B9

B9 --> B10

B10 -->|"Reference request"| B11

B11 --> B12

B12 -->|"Signed - onboarding"| B13

B13 --> B14
B14 --> B15

%% Offer-declined loop
B12 -.->|"Offer declined > repost"| B4


%% =========================================================
%% VISUAL GROUPING / STYLE
%% =========================================================

classDef hiring fill:#ffffff,stroke:#333,stroke-width:1px;
classDef recruiting fill:#ffffff,stroke:#333,stroke-width:1px;
classDef operations fill:#ffffff,stroke:#333,stroke-width:1px;

class B1,B9,B10 hiring;
class B2,B3,B4,B5,B6,B8,B11,B12 recruiting;
class B13,B14,B15 operations;