# Fintrak — Finance Dashboard

A clean, professional single-page finance dashboard built with vanilla HTML, CSS, and JavaScript.
The live preview link is https://finance-ui-dashboard-blond.vercel.app/

## Setup

No build tools or dependencies needed. Just open `index.html` in any modern browser.

## Features

### Dashboard Overview
- **4 Summary Cards**: Total Balance, Income, Expenses, Savings Rate — with month-over-month trend indicators
- **Balance Trend Chart**: Line chart showing 6 months of income vs expenses
- **Spending Donut Chart**: Category breakdown with percentage legend
- **Quick Insights**: Top spending category, current month summary, smart observation

### Transactions
- Full transaction table with Description, Category, Type, Amount, Date
- **Filtering**: By type (Income/Expense), Category, Month
- **Sorting**: Click any column header to sort ascending/descending
- **Search**: Live search across name, category, note fields
- **Pagination**: 8 rows per page with smart page controls
- **Admin Actions**: Edit and Delete buttons (visible to Admin role only)
- **Add Transaction**: Modal form with all fields (Admin only)

### Role-Based UI
- **Admin**: Can add, edit, and delete transactions. Sees admin banner and action buttons.
- **Viewer**: Read-only mode. Action buttons hidden. Switch via sidebar dropdown.
- Role is persisted in localStorage.

### Insights
- Monthly Income vs Expenses bar chart
- Category spending progress bars
- 6-month summary table with net change %
- Key observations panel (top category, trend analysis, savings rate, activity)

### Additional Features
- **Dark/Light Mode**: Toggle from sidebar or topbar icon, persisted in localStorage
- **Data Persistence**: All transactions saved to localStorage automatically
- **Export CSV**: Download filtered transactions as CSV
- **Seed Data**: 6 months of realistic mock data pre-loaded on first visit
- **Responsive**: Works on mobile, tablet, and desktop
- **Empty States**: Graceful handling when no data matches filters

## State Management

Pure JavaScript state object with no framework:
```js
state = {
  transactions: [],   // All transaction records
  role: 'admin',      // 'admin' | 'viewer'
  filters: {},        // Active filter values
  sort: {},           // Current sort field + direction
  page: 1,            // Current pagination page
  theme: 'dark',      // UI theme
}
```
All state changes call `renderAll()` to re-render affected components. State is persisted via `localStorage`.

## Design

- **Aesthetic**: Luxury dark theme with gold accents
- **Fonts**: Playfair Display (headings) + DM Sans (body) + JetBrains Mono (numbers)
- **Charts**: Chart.js 4 via CDN
- **No framework dependencies** — pure HTML/CSS/JS
