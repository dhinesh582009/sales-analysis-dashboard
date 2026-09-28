# Sales Pulse

Build a professional Sales Analytics Dashboard web app.

DATABASE SCHEMA (Supabase/Postgres):

- categories: id, name

- products: id, name, category_id (FK), price, cost, stock_quantity

- customers: id, name, email, region, segment, created_at

- sales: id, product_id (FK), customer_id (FK), quantity, unit_price,

  total_amount, profit, sale_date, payment_method, status

Seed with ~400 realistic rows: 5 categories, 20+ products, 50+ customers

across 5 regions, dates spanning the last 12 months, with believable

seasonal variation in volume.

CORE PAGES & FEATURES:

1. Dashboard (home)

   - 4 KPI cards: Total Revenue, Total Orders, Avg Order Value, Profit

     Margin — each showing % change vs previous period with up/down arrow

   - Line chart: Revenue trend over last 12 months

   - Bar chart: Sales by category

   - Donut chart: Revenue by region

   - Top 5 products table (name, units sold, revenue, % of total)

   - Recent transactions table (last 10, with status badges)

2. Global filter bar (persists across dashboard)

   - Date range picker (with presets: 7d/30d/90d/12mo/custom)

   - Region multi-select

   - Category multi-select

   - All charts, KPIs, and tables update reactively on filter change

3. Products page

   - Full product table: searchable, sortable by any column, paginated

   - Per-product mini stats: units sold, revenue, stock level indicator

   - Add/Edit/Delete product (simple modal form)

4. Customers page

   - Customer table: total spend, order count, last order date, segment

   - Click a customer to see their order history

5. Export

   - "Export as CSV" button on tables and on the filtered dashboard data

DESIGN REQUIREMENTS:

- Modern SaaS dashboard aesthetic (Stripe/Linear/Vercel style)

- Collapsible dark sidebar nav + light content area, with a dark mode

  toggle for the whole app

- Card-based layout, subtle shadows, rounded corners, consistent spacing

- Primary accent: deep indigo/blue; green for positive trends, red for

  negative

- Clean sans-serif font (Inter or similar), clear typographic hierarchy

- Fully responsive — sidebar collapses to bottom nav or hamburger on mobile

- Loading skeletons for charts/tables while data fetches

- Empty states for tables/charts when filters return no data

TECH:

- React 19 + TanStack Start & Router
- Tailwind CSS (Slate Navy + Amber Theme)
- Python Flask API + SQLAlchemy ORM + MySQL
- JWT Session Authentication & Role-Based Access Control (`admin` vs `user`)
- SMTP Email Verification (Gmail & Local Test Receiver)
- Recharts for data visualizations
- Sonner toast notifications for user interactions

## Architecture & Features

- **Public Landing Page**: Modern overview with value proposition and feature highlights.
- **Enterprise Dashboard**: Revenue KPI cards, category breakdown, trend charts, and sales velocity metrics.
- **Role-Based Catalogue Management**: Non-admins browse catalogue; verified admins can create, edit, and delete products.
- **Customer Intelligence**: Detailed customer spend metrics and interactive order history drill-down modal.
- **Bulletproof Auth**: Rate limiting / lockout protection, secure email verification, and session persistence.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
