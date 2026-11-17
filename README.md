# Margao Fitness & Strength Club — Membership Dashboard

A high-performance, responsive gym management and membership analytics dashboard built specifically for **Margao Fitness & Strength Club** (Colva Road, Margao, Goa). 

Designed with zero external dependencies—utilizing pure HTML5 `<canvas>` rendering APIs, vanilla ES6 JavaScript, and responsive CSS Grid layout—it runs instantly in any modern browser or mobile device.

---

## 📂 Project Structure

```text
├── dashboard.html   # Main application shell, top bar controls, KPI cards, canvas viewports, and table
├── style.css        # Dark-mode athletic theme, CSS variables, typography, and responsive media queries
├── data.js          # Realistic 6-month dataset (June – November 2026) in INR (₹)
├── app.js           # Core reactive filter engine, KPI aggregator, custom canvas charts & CSV export
└── README.md        # Technical documentation, dataset specs, and user guide




//Dataset Specification (data.js)

The dataset simulates a boutique fitness club in South Goa with 36 distinct member profiles across 6 active fitness programs spanning June 1, 2026 to November 30, 2026 (referenced to November 17, 2026):

Classes Tracked: HIIT, CrossFit, Yoga, Zumba, Strength Training, and Spin.

Membership Plans: Monthly (₹1,800–₹1,900), Quarterly (₹4,700–₹5,200), Annual (₹13,800–₹16,000), and Personal Training (₹9,500–₹10,200).

Attendance Records: Monthly check-in counts vs. maximum slot capacities across all 6 months, enabling accurate utilization rates.

Financial Logs: Invoice records tied to payment months for precise monthly and cumulative revenue calculations.




Custom Chart Logic (No Libraries)
Instead of bloated third-party charting libraries, this dashboard implements custom 2D rendering engines on HTML5 <canvas> elements:

A. Membership Growth Line Chart (growthCanvas)
Retina Scaling: Dynamically multiplies canvas backing resolution by window.devicePixelRatio for razor-sharp crispness on high-DPI smartphone and laptop screens.

Dual Metrics: Draws an Emerald green line & filled gradient area for Active Members alongside a Dashed Amber line tracking New Joiners month-over-month.

Interactive Tooltips: Calculates proximity to nearest data points on mouse move, rendering precise floating tooltips with active counts and joiner stats.

B. Attendance by Class Bar Chart (attendanceCanvas)
Utilization Percentage: Computes check-ins divided by class capacity, rendering rounded-top pillar bars with live percentage badges.

Click-to-Filter: Clicking any class bar instantly updates the global dashboard filter to isolate that specific class across all KPIs, growth trends, and tables.





How to Read & Use the Dashboard
Top Filter Controls:

Month Dropdown: Switch between individual months (June – November 2026) or select All 6 Months to aggregate year-to-date data.

Class Dropdown: Focus analytics on a single program (e.g., Strength Training, CrossFit, Yoga).

Search Bar: Instantly filter the expiring memberships watchlist by member name, ID (MRG-1xx), or plan type.

KPI Stat Cards:

Active Members: Total valid memberships in the selected period, complete with month-over-month growth percentage badge.

New Joiners: Total signups onboarded during the active filter window.

Avg. Attendance Rate: Aggregate check-ins vs. total available class capacity.

Revenue (INR): Total fee collections formatted in Indian numbering (₹1,45,000+).

Expiring Memberships Watchlist:

Sorted chronologically by expiry date to help front-desk staff proactively contact members for renewals.

Color-coded status badges: Active (>15 days left), Expiring Soon (≤15 days), and Expired.

CSV Export:

Click the Export CSV button in the top right to instantly download a standards-compliant .csv file containing all filtered member records matching your current month/class/search criteria