<!-- myTruv: Financial Insight Taxonomy + SEO & Content Strategy -->

# myTruv — Financial Insight Taxonomy & SEO / Content Strategy

Working doc for:

- financial insight taxonomy (FI Type / FI Subtype / Action),
- classification prompts,
- SEO & content strategy for myTruv.

---

## 1. Financial Insight Taxonomy (by Intent)

Here is the taxonomy “like Claude’s JSON, but for myTruv and grouped by intent”.

Each **Intent** groups a set of **Insight Types** and **Subcategories** that become:

- `FI Type`  = `insight_types.name`
- `FI Subtype` = each entry in `subcategories`

You’ll use these in prompts, DB schemas and UI labels.

---

### 1.1. SAFETY_CHECK – “Am I basically okay?”

**Goal:** one calm answer to “Am I safe / okay?” without shame.

**JSON:**

~~~json
{
  "id": "SAFETY_CHECK",
  "name": "Safety & Calm Check",
  "description": "Answering 'Am I basically okay?' based on Truv Score, cushion and stability.",
  "insight_types": [
    {
      "id": "SYSTEM_HEALTH",
      "name": "Overall System Health",
      "subcategories": [
        "TRUV_SCORE_STATUS",
        "SCORE_TREND_CHANGE",
        "RUNWAY_ESTIMATE",
        "HEAVY_MONTH_BUT_SAFE"
      ]
    },
    {
      "id": "CUSHION_STATUS",
      "name": "Cushion & Safety Net",
      "subcategories": [
        "LOW_OR_NO_EMERGENCY_FUND",
        "CUSHION_IMPROVING_TREND",
        "CUSHION_BEING_QUIETLY_USED",
        "CUSHION_PROTECTED_FROM_NEW_DEBT"
      ]
    },
    {
      "id": "STABILITY_PATTERN",
      "name": "Stability & Volatility",
      "subcategories": [
        "HIGH_MONTH_TO_MONTH_VOLATILITY",
        "STABILITY_IMPROVING",
        "ONE_OFF_SPIKE_EXPLAINED",
        "NEW_BASELINE_SHIFT_DETECTED"
      ]
    }
  ]
}
~~~

---

### 1.2. QUICK_WINS – “Show me easy wins & leaks”

**Goal:** high‑ROI, low‑effort fixes (subscriptions, fees, small leaks).

**JSON:**

~~~json
{
  "id": "QUICK_WINS",
  "name": "Quick Wins & Leak Fixes",
  "description": "Fast, low-hassle wins: kill leaks, reduce dumb costs, capture obvious opportunities.",
  "insight_types": [
    {
      "id": "SUBSCRIPTION_LEAKS",
      "name": "Subscriptions & Recurring",
      "subcategories": [
        "SUBSCRIPTION_REDUNDANCY",
        "SUBSCRIPTION_UNDERUTILIZED",
        "SUBSCRIPTION_HIDDEN_OR_FORGOTTEN",
        "SUBSCRIPTION_PRICE_INCREASE",
        "FREE_TRIAL_ABOUT_TO_START_CHARGING"
      ]
    },
    {
      "id": "BANK_FEES_LEAKS",
      "name": "Banking & Fee Leaks",
      "subcategories": [
        "CHECKING_ACCOUNT_FEES",
        "ATM_FEE_PATTERN",
        "OVERDRAFT_PATTERN_DETECTED",
        "FOREIGN_TRANSACTION_FEES",
        "WIRE_TRANSFER_EXCESSIVE"
      ]
    },
    {
      "id": "DAILY_SPEND_LEAKS",
      "name": "Everyday Spending Leaks",
      "subcategories": [
        "SMALL_DAILY_PURCHASES_ADD_UP",
        "DELIVERY_CREEP_PATTERN",
        "CATEGORY_OVERSPEND_VS_SELF_BASELINE",
        "IMPULSE_SPENDING_PATTERN"
      ]
    },
    {
      "id": "YIELD_LEAKS",
      "name": "Cash Yield & Idle Money",
      "subcategories": [
        "IDLE_CASH_DETECTED",
        "SAVINGS_RATE_SUBOPTIMAL",
        "LOW_YIELD_CHECKING_BALANCE_HIGH",
        "MOVE_CASH_TO_HIGH_YIELD_OPPORTUNITY"
      ]
    }
  ]
}
~~~

---

### 1.3. CASHFLOW_STABILITY – “Make my system more stable”

**Goal:** smooth noisy income & big bills, build buffers, explain weird months.

**JSON:**

~~~json
{
  "id": "CASHFLOW_STABILITY",
  "name": "Cashflow & Cushion Building",
  "description": "Smoothing chaos: irregular income, bad bill timing, big shocks – so the system feels stable.",
  "insight_types": [
    {
      "id": "CASHFLOW_TIMING",
      "name": "Income & Bill Timing",
      "subcategories": [
        "BILL_CYCLE_ALIGNMENT_ISSUE",
        "PAYCHECK_AND_BILLS_MISALIGNED",
        "LARGE_PAYMENTS_CLUSTERED",
        "INCOME_SMOOTHING_OPPORTUNITY"
      ]
    },
    {
      "id": "BUFFER_PLANNING",
      "name": "Buffers & Future Shocks",
      "subcategories": [
        "TAX_BUFFER_INSUFFICIENT",
        "IRREGULAR_EXPENSE_BUFFER_MISSING",
        "UPCOMING_KNOWN_BIG_BILL",
        "SEASONAL_EXPENSE_PATTERN"
      ]
    },
    {
      "id": "SAVINGS_BEHAVIOR",
      "name": "Savings & Cushion Behavior",
      "subcategories": [
        "IRREGULAR_SAVINGS_PATTERN",
        "NO_AUTOMATIC_SAVINGS",
        "SAVINGS_VS_DEBT_TRADEOFF_OFF",
        "SHORT_TERM_GOAL_UNDERFUNDED"
      ]
    },
    {
      "id": "BIG_EVENT_STORIES",
      "name": "Trips & Life Event Stories",
      "subcategories": [
        "TRAVEL_TRIP_COST_SUMMARY",
        "MOVE_APARTMENT_COST_SUMMARY",
        "CAR_REPAIR_COST_IMPACT",
        "MEDICAL_BILL_IMPACT",
        "GADGET_OR_FURNITURE_UPGRADE_IMPACT"
      ]
    }
  ]
}
~~~

---

### 1.4. RISK_REDUCTION – “Reduce risk & expensive stress”

**Goal:** reduce chances of expensive pain: bad debt, credit issues, insurance gaps, fraud.

**JSON:**

~~~json
{
  "id": "RISK_REDUCTION",
  "name": "Risk & Stress Reduction",
  "description": "Reducing chances of big pain: expensive debt, credit risk, coverage gaps, fraud and identity issues.",
  "insight_types": [
    {
      "id": "DEBT_STRESS",
      "name": "Debt Cost & Structure",
      "subcategories": [
        "HIGH_INTEREST_DEBT_BURDEN",
        "PAYMENT_ORDER_SUBOPTIMAL",
        "REFINANCE_OR_CONSOLIDATION_OPPORTUNITY",
        "MISSED_OR_LATE_PAYMENTS_RISK",
        "BNPL_OVERUSE_PATTERN"
      ]
    },
    {
      "id": "CREDIT_HEALTH",
      "name": "Credit Score & Behavior",
      "subcategories": [
        "HIGH_CREDIT_UTILIZATION",
        "TOO_MANY_RECENT_INQUIRIES",
        "NEGATIVE_MARKS_PRESENT",
        "THIN_CREDIT_FILE",
        "CARD_REWARDS_SUBOPTIMAL"
      ]
    },
    {
      "id": "INSURANCE_GAPS",
      "name": "Insurance & Protection",
      "subcategories": [
        "INSURANCE_GAP_IDENTIFIED",
        "INSURANCE_OVERLAP_DETECTED",
        "DEDUCTIBLE_NOT_ALIGNED_WITH_RISK",
        "CRITICAL_COVERAGE_MISSING"
      ]
    },
    {
      "id": "FRAUD_IDENTITY",
      "name": "Fraud, Identity & P2P Risk",
      "subcategories": [
        "IDENTITY_THEFT_RISK_PATTERN",
        "SUSPICIOUS_P2P_TRANSFERS",
        "LACK_OF_DIGITAL_FOOTPRINT_FOR_CASH",
        "CREDIT_MONITORING_RECOMMENDED"
      ]
    }
  ]
}
~~~

---

### 1.5. GROWTH_UPGRADE – “Help me grow & upgrade my system”

**Goal:** not just fixing problems, but using benefits, taxes, investing, income and learning to level up.

**JSON:**

~~~json
{
  "id": "GROWTH_UPGRADE",
  "name": "Growth, Benefits & Learning",
  "description": "Using taxes, benefits, investing, income and knowledge to make the system stronger over time.",
  "insight_types": [
    {
      "id": "TAX_OPPORTUNITIES",
      "name": "Tax Optimization & Credits",
      "subcategories": [
        "TAX_WITHHOLDING_ADJUSTMENT",
        "TAX_DEDUCTION_MISSED",
        "TAX_CREDIT_ELIGIBLE",
        "EDUCATION_OR_STUDENT_LOAN_TAX_BENEFIT",
        "RSU_OR_EQUITY_TAX_DRAG"
      ]
    },
    {
      "id": "BENEFITS_AND_ACCOUNTS",
      "name": "Employer & Tax-Advantaged Accounts",
      "subcategories": [
        "401K_MATCH_NOT_MAXIMIZED",
        "HSA_FSA_UNDERUTILIZED",
        "COMMUTER_BENEFIT_UNCLAIMED",
        "ESPP_NOT_ENROLLED",
        "GOV_ASSISTANCE_OR_PROGRAM_ELIGIBLE"
      ]
    },
    {
      "id": "INVESTING_UPGRADE",
      "name": "Investing & Long-Term Growth",
      "subcategories": [
        "NOT_INVESTING_WITH_AVAILABLE_SURPLUS",
        "INVESTMENT_FEE_HIGH",
        "ASSET_ALLOCATION_MISALIGNED",
        "TOO_MUCH_CASH_VS_LONG_TERM",
        "DCA_OR_AUTOMATION_OPPORTUNITY"
      ]
    },
    {
      "id": "INCOME_AND_SKILLS",
      "name": "Income, Skills & Career",
      "subcategories": [
        "SIDE_INCOME_OPPORTUNITY",
        "RAISE_NEGOTIATION_TIMING",
        "FREELANCE_TAX_OPTIMIZATION",
        "EMPLOYER_EDUCATION_BENEFITS_UNUSED"
      ]
    },
    {
      "id": "HABITS_EDUCATION",
      "name": "Habits & Education Progress",
      "subcategories": [
        "EDUCATION_GAP_ON_CORE_TOPICS",
        "LOW_ENGAGEMENT_WITH_LEARNING_CONTENT",
        "IMPROVEMENT_TREND_BUT_NOT_STABLE",
        "STRONG_DISCIPLINE_AND_STREAKS"
      ]
    }
  ]
}
~~~

---

## 2. Mapping to FI Type / FI Subtype

For the classification prompts, you can use:

- **FI Type** = `insight_types.name`  
  (e.g. `"Subscriptions & Recurring"`, `"Debt Cost & Structure"`, `"Trips & Life Event Stories"`)

- **FI Subtype** = each value in `subcategories`  
  (e.g. `"SUBSCRIPTION_HIDDEN_OR_FORGOTTEN"`, `"HIGH_CREDIT_UTILIZATION"`, `"TRAVEL_TRIP_COST_SUMMARY"`)

So the flat lists for prompts look like this:

---

### 2.1. FI Type values (20 types)

Use these strings in `{ONE OF THE FOLLOWING}` for `FI Type`:

- Overall System Health
- Cushion & Safety Net
- Stability & Volatility
- Subscriptions & Recurring
- Banking & Fee Leaks
- Everyday Spending Leaks
- Cash Yield & Idle Money
- Income & Bill Timing
- Buffers & Future Shocks
- Savings & Cushion Behavior
- Trips & Life Event Stories
- Debt Cost & Structure
- Credit Score & Behavior
- Insurance & Protection
- Fraud, Identity & P2P Risk
- Tax Optimization & Credits
- Employer & Tax-Advantaged Accounts
- Investing & Long-Term Growth
- Income, Skills & Career
- Habits & Education Progress

(You can merge a couple if you want fewer FI Types, but this size is still very manageable.)

---

### 2.2. FI Subtype values (all subcategories)

For the `FI Subtype` prompt you’ll have a longer `{ONE OF THE FOLLOWING}` list.

Values are all caps here, but you can keep them as readable phrases if you prefer:

- TRUV_SCORE_STATUS
- SCORE_TREND_CHANGE
- RUNWAY_ESTIMATE
- HEAVY_MONTH_BUT_SAFE
- LOW_OR_NO_EMERGENCY_FUND
- CUSHION_IMPROVING_TREND
- CUSHION_BEING_QUIETLY_USED
- CUSHION_PROTECTED_FROM_NEW_DEBT
- HIGH_MONTH_TO_MONTH_VOLATILITY
- STABILITY_IMPROVING
- ONE_OFF_SPIKE_EXPLAINED
- NEW_BASELINE_SHIFT_DETECTED
- SUBSCRIPTION_REDUNDANCY
- SUBSCRIPTION_UNDERUTILIZED
- SUBSCRIPTION_HIDDEN_OR_FORGOTTEN
- SUBSCRIPTION_PRICE_INCREASE
- FREE_TRIAL_ABOUT_TO_START_CHARGING
- CHECKING_ACCOUNT_FEES
- ATM_FEE_PATTERN
- OVERDRAFT_PATTERN_DETECTED
- FOREIGN_TRANSACTION_FEES
- WIRE_TRANSFER_EXCESSIVE
- SMALL_DAILY_PURCHASES_ADD_UP
- DELIVERY_CREEP_PATTERN
- CATEGORY_OVERSPEND_VS_SELF_BASELINE
- IMPULSE_SPENDING_PATTERN
- IDLE_CASH_DETECTED
- SAVINGS_RATE_SUBOPTIMAL
- LOW_YIELD_CHECKING_BALANCE_HIGH
- MOVE_CASH_TO_HIGH_YIELD_OPPORTUNITY
- BILL_CYCLE_ALIGNMENT_ISSUE
- PAYCHECK_AND_BILLS_MISALIGNED
- LARGE_PAYMENTS_CLUSTERED
- INCOME_SMOOTHING_OPPORTUNITY
- TAX_BUFFER_INSUFFICIENT
- IRREGULAR_EXPENSE_BUFFER_MISSING
- UPCOMING_KNOWN_BIG_BILL
- SEASONAL_EXPENSE_PATTERN
- IRREGULAR_SAVINGS_PATTERN
- NO_AUTOMATIC_SAVINGS
- SAVINGS_VS_DEBT_TRADEOFF_OFF
- SHORT_TERM_GOAL_UNDERFUNDED
- TRAVEL_TRIP_COST_SUMMARY
- MOVE_APARTMENT_COST_SUMMARY
- CAR_REPAIR_COST_IMPACT
- MEDICAL_BILL_IMPACT
- GADGET_OR_FURNITURE_UPGRADE_IMPACT
- HIGH_INTEREST_DEBT_BURDEN
- PAYMENT_ORDER_SUBOPTIMAL
- REFINANCE_OR_CONSOLIDATION_OPPORTUNITY
- MISSED_OR_LATE_PAYMENTS_RISK
- BNPL_OVERUSE_PATTERN
- HIGH_CREDIT_UTILIZATION
- TOO_MANY_RECENT_INQUIRIES
- NEGATIVE_MARKS_PRESENT
- THIN_CREDIT_FILE
- CARD_REWARDS_SUBOPTIMAL
- INSURANCE_GAP_IDENTIFIED
- INSURANCE_OVERLAP_DETECTED
- DEDUCTIBLE_NOT_ALIGNED_WITH_RISK
- CRITICAL_COVERAGE_MISSING
- IDENTITY_THEFT_RISK_PATTERN
- SUSPICIOUS_P2P_TRANSFERS
- LACK_OF_DIGITAL_FOOTPRINT_FOR_CASH
- CREDIT_MONITORING_RECOMMENDED
- TAX_WITHHOLDING_ADJUSTMENT
- TAX_DEDUCTION_MISSED
- TAX_CREDIT_ELIGIBLE
- EDUCATION_OR_STUDENT_LOAN_TAX_BENEFIT
- RSU_OR_EQUITY_TAX_DRAG
- 401K_MATCH_NOT_MAXIMIZED
- HSA_FSA_UNDERUTILIZED
- COMMUTER_BENEFIT_UNCLAIMED
- ESPP_NOT_ENROLLED
- GOV_ASSISTANCE_OR_PROGRAM_ELIGIBLE
- NOT_INVESTING_WITH_AVAILABLE_SURPLUS
- INVESTMENT_FEE_HIGH
- ASSET_ALLOCATION_MISALIGNED
- TOO_MUCH_CASH_VS_LONG_TERM
- DCA_OR_AUTOMATION_OPPORTUNITY
- SIDE_INCOME_OPPORTUNITY
- RAISE_NEGOTIATION_TIMING
- FREELANCE_TAX_OPTIMIZATION
- EMPLOYER_EDUCATION_BENEFITS_UNUSED
- EDUCATION_GAP_ON_CORE_TOPICS
- LOW_ENGAGEMENT_WITH_LEARNING_CONTENT
- IMPROVEMENT_TREND_BUT_NOT_STABLE
- STRONG_DISCIPLINE_AND_STREAKS

---

## 3. Recommended Action Types (for the Action prompt)

These are the single‑choice “what to do” labels you can use across all intents:

- Rebalance Monthly Budget
- Reduce Discretionary Spending
- Cut or Cancel Subscriptions
- Optimize Subscription Plan or Tier
- Move Cash to High-Yield Savings
- Build or Increase Emergency Fund
- Pay Down High-Interest Debt First
- Refinance or Consolidate Debt Strategically
- Optimize Credit Card Usage and Rewards
- Lower Credit Utilization and Avoid New Debt
- Enroll in or Increase Employer Retirement Contributions
- Open or Fund HSA / FSA or Other Tax-Advantaged Account
- Adjust Tax Withholding or Filing Strategy
- Switch to Lower-Fee / Higher-Interest Bank Account
- Reduce Bank / ATM / Foreign Transaction Fees
- Review and Adjust Insurance Coverage
- Set Up Automation (Autopay, Autosave, Alerts)
- Increase Income (Raise, Side Gig, Monetize Skills)
- Protect Identity and Credit (Monitoring / Freeze / Alerts)
- Create or Update a Financial Plan for a Specific Goal

---

## 4. myTruv — SEO & Content Strategy (No‑Hustle AI Autopilot + One Score)

### 4.1. Purpose

This file defines how myTruv shows up in **search** and **content**:

- what topics we want to own,
- what keywords we aim for,
- how content supports the brand story:
  - AI money companion,
  - no‑hustle,
  - one calm score,
  - works with messy/irregular income,
  - emotionally safe and shame‑free.

Use this for:

- planning blog posts & content hubs,
- writing landing pages & `/vs` pages,
- briefing writers / agencies.

---

### 4.2. Global SEO Principles

1. **Start from real emotional problems**
   - “Budgeting apps exhaust me.”
   - “I have irregular income.”
   - “I feel anxious about money.”
   - “I don’t know what my trip/move actually cost.”

2. **Tie every topic back to our promise**
   - no‑hustle,
   - one score & one scroll,
   - AI autopilot,
   - shame‑free.

3. **Avoid clickbait and guilt**
   - No “Fix your bad money habits” headlines.
   - Focus on *relief*, *clarity*, *small steps*.

---

### 4.3. Cluster: No‑Hustle / Autopilot Money Management

**Keyword ideas**

- no hustle money management
- low effort money management
- simple way to see my finances
- money app without budgeting
- money overview in one screen
- check my finances at a glance
- automatic money management app
- AI money companion
- money app that runs on autopilot

**Content ideas**

- “No‑hustle money management: why you don’t need another budgeting app”
- “What a financial autopilot looks like in real life (and what it’s not)”
- “How to check your whole money situation in one scroll”
- “From spreadsheets to autopilot: turning your existing tools into a system”
- “AI money companion vs. classic budgeting app: which one do you actually need?”

---

### 4.4. Cluster: One Financial Health / Money Wellbeing Score

**Keyword ideas**

- financial health score app
- money wellbeing score
- money score app
- personal finance score like credit score
- see my financial health in one number
- financial wellness score
- alternative to credit score for money health

**Content ideas**

- “Why a single financial wellbeing score is easier to live with than ten dashboards”
- “Credit score vs money wellbeing score: what’s the difference?”
- “How one calm number can reduce money anxiety”
- “What goes into a money wellbeing score (without exposing your raw numbers)”
- “Income vs system health: why your salary isn’t the whole story”

---

### 4.5. Cluster: Irregular / Fluctuating Income

**Keyword ideas**

- budgeting with irregular income
- manage money when income fluctuates
- app for freelancers with irregular income
- how to manage money with variable income
- cashflow overview without detailed budgeting
- money management for self‑employed
- AI cashflow assistant

**Content ideas**

- “Irregular income, simple picture: how to see if you’re still okay”
- “You don’t need a perfect budget to understand your money with variable income”
- “One glance, not a spreadsheet: money clarity for freelancers and creators”
- “How an AI money autopilot can smooth your cashflow ups and downs”
- “Self‑employed, chaotic income: building buffers without becoming your own accountant”

---

### 4.6. Cluster: Money Anxiety, Guilt & Avoidance

**Keyword ideas**

- money anxiety app
- app to feel calmer about money
- stressed about money but don’t want budgeting
- overwhelmed by budgeting apps
- money guilt
- avoid looking at bank account
- money app that doesn’t shame you

**Content ideas**

- “You don’t need more spreadsheets. You need to know you’re okay.”
- “A gentle money app: how myTruv avoids shaming you”
- “From panic to ‘it’s fine’: how one score can ease money anxiety”
- “Why classic budgeting apps can make money anxiety worse”
- “How to check your bank account without spiralling into guilt”

---

### 4.7. Cluster: Trips & Life Events (Vegas / Cancun / Disney, moves, repairs)

**Keyword ideas**

- track vacation spending automatically
- how much did my Vegas weekend cost
- how much did my Cancun trip cost
- see how much I spent on Disney trip
- categorize travel expenses automatically
- see how much I spent on vacation
- how much did my move cost
- track cost of moving apartments
- track car repair costs automatically
- medical bill impact on finances

**Content ideas**

- “How to find out what your Vegas weekend or Cancun trip really cost (without building a spreadsheet)”
- “Connect your bank, see your Disney trip — no manual work”
- “Trip stories, not transaction dumps: a humane way to see your travel spending”
- “What your move / car repair / medical bill actually did to your financial health”
- “From bachelorette weekends to family beach trips: turning messy card swipes into clear stories”

---

### 4.8. Cluster: Alternatives to Budgeting & Gamified Finance Apps

**Keyword ideas**

- alternative to budgeting apps
- budgeting apps don’t work for me
- tired of budgeting app
- hate budgeting app
- finance app without gamification
- money app without streaks
- app like Credit Karma but for overall finances

**Content ideas**

- “Why budgeting apps and daily streaks don’t work for everyone”
- “You don’t need financial rings — you need one calm score”
- “If budgeting apps make you feel guilty, try a no‑hustle alternative”
- “Credit Karma for your whole money life: one score, not just your debt”
- “Gamification vs gentle progress: designing money tools that people actually open”

---

### 4.9. Cluster: Quick Check‑ins for Busy People

**Keyword ideas**

- quick way to check my finances
- see all my money in one place quickly
- money overview for busy professionals
- personal finance app for people with no time
- check finances in 30 seconds

**Content ideas**

- “How to check your whole money situation in under 30 seconds”
- “One score, one scroll: the busy person’s money check‑in”
- “Why your money app should feel more like a weather check than a weekly ritual”
- “From Sunday money reviews to 30‑second AI check‑ins”

---

### 4.10. Cluster: Students & Early‑Stage Adults

**Keyword ideas**

- money app for students
- how to manage money in college
- first job money mistakes
- simple money app for beginners
- I feel behind with money in my 20s

**Content ideas**

- “You’re not behind: a kind money guide for your 20s”
- “First job, first paycheck: a low‑stress way to watch your money”
- “How to see if you’re okay with money without turning into a finance nerd”
- “What our money score tells you if you’re just starting out”

---

### 4.11. Site & Content Structure

#### 4.11.1. Core pages

- `/` — Home  
  **H1 examples:**
  - “See your money in one score and one scroll.”
  - “AI‑powered, no‑hustle money companion.”

  **Above‑the‑fold:**
  - one calm score,
  - autopilot,
  - works with messy income,
  - shame‑free.

- `/product` — How no‑hustle financial autopilot works
- `/product/score` — Financial wellbeing score
- `/product/overview` — One‑scroll overview
- `/product/autopilot` — Behavior autopilot & AI
- `/product/stories` — Trips & life events view

#### 4.11.2. Use‑case pages

- `/use-cases/irregular-income`
- `/use-cases/anxious-about-money`
- `/use-cases/travel-spending`
- `/use-cases/busy-professionals`
- `/use-cases/exhausted-power-users`

#### 4.11.3. Comparison pages

- `/vs/budgeting-apps`
- `/vs/gamified-finance`
- `/vs/spreadsheets`

#### 4.11.4. Blog clusters

- no‑hustle money management
- financial wellbeing score
- irregular income & cashflow
- money anxiety & emotional safety
- trips & life events
- alternatives to budgeting tools
- quick money check‑ins

---

### 4.12. Tone for SEO Content

Same calm, supportive tone as product:

- Avoid “fix your bad habits” / “stop wasting money”.
- Prefer “see your situation clearly”, “feel okay looking at your accounts”.

Every piece should:

1. Start from a **real emotional pain**.
2. Explain why classic tools feel heavy or shaming.
3. Introduce **one score + one scroll + AI autopilot** as a softer alternative.
4. End with a **gentle CTA**, e.g.:

   > “If you’re tired of budgeting apps but still want to know you’re okay, myTruv might be the next thing to try.”
