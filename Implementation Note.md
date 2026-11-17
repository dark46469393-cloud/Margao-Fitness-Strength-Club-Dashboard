How It Works
Modular Architecture: The application is split into four clean files (dashboard.html for structure, style.css for dark-mode athletic styling, data.js for structured local datasets, and app.js for reactive filtering, state management, canvas rendering, and CSV generation).

Reactive Filtering Engine (app.js): Changing either the Month or Class dropdown instantly triggers a recalculation pipeline. It filters membership records, recomputes KPI aggregates (Active members, New joiners, Attendance %, and Revenue in INR), redraws both canvas charts, and filters/sorts the expiring memberships watchlist table in real time.

Pure HTML5 <canvas> Rendering: Bypasses heavy external charting libraries (like Chart.js or D3) to maintain zero installation friction. It features automatic Retina display scaling (window.devicePixelRatio), horizontal/vertical grid lines, gradient area fills, dashed comparison lines, hover tooltips, and click-to-filter bar interactions.

2. Key Design Decisions
Zero Dependencies: Pure vanilla ES6 and native browser APIs ensure the dashboard loads instantly and runs smoothly on any modern browser, even offline or on low-end hardware at the gym front desk.

Local Relevance: Built with authentic Goan/Indian names (MRG-1xx), Goan locality context (Colva Road, Margao), and INR (₹) currency formatting using Indian numbering separators (en-IN).

Mobile-First Responsiveness: Designed using CSS Grid and Flexbox with dedicated breakpoints to reflow stat cards and shrink table views gracefully down to 360px (tested for iPhone SE and budget Android viewports).

3. How to Test
Save all four files (dashboard.html, style.css, data.js, app.js) in the exact same folder on your computer.

Double-click dashboard.html to open it in Chrome, Safari, Firefox, or Edge.

Test Filters: Change the month filter to June 2026 or class filter to Strength Training—observe all KPIs, charts, and table rows update simultaneously.

Test Canvas Interactivity: Hover over the growth chart line or attendance bars to inspect tooltips. Click any bar on the attendance chart to instantly filter by that class.

Test Mobile View (360px): Press F12 to open browser DevTools, toggle Device Toolbar (Ctrl+Shift+M or Cmd+Shift+M), set width to 360px, and verify touch-friendly layout and table horizontal scrolling.

Test CSV Export: Click the green Export CSV button in the top right and verify that the downloaded .csv file contains exactly the filtered dataset currently visible on screen.