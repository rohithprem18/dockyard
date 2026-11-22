<div align="center">

<img src="./public/readme-banner.svg" alt="DockYard — the operational command center for inventory" width="100%" />

<br/>

[![React](https://img.shields.io/badge/React-19-149eca?style=flat-square&logo=react&logoColor=white)](https://react.dev)
[![TypeScript](https://img.shields.io/badge/TypeScript-6-3178c6?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org)
[![Vite](https://img.shields.io/badge/Vite-8-646cff?style=flat-square&logo=vite&logoColor=white)](https://vitejs.dev)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-4-06b6d4?style=flat-square&logo=tailwindcss&logoColor=white)](https://tailwindcss.com)
[![pnpm](https://img.shields.io/badge/pnpm-package_manager-f69220?style=flat-square&logo=pnpm&logoColor=white)](https://pnpm.io)
[![Deploy with Vercel](https://img.shields.io/badge/Deploy-Vercel-000000?style=flat-square&logo=vercel&logoColor=white)](https://vercel.com/new)
[![License](https://img.shields.io/badge/license-private-6b6663?style=flat-square)](#license)

</div>

<br/>

## What is DockYard?

DockYard is an inventory and warehouse operations platform for small and medium
businesses. It replaces the spreadsheet-and-guesswork approach to stock
management with a single, fast interface for the day-to-day work of running a
warehouse: knowing what you have, where it is, what's running low, and what
happened to it.

It isn't a generic CRUD dashboard. Every screen is built around one question —
*what does this user need to decide or do right now?* — with the visual
density and speed of tools like Linear, Stripe Dashboard, and Shopify Admin:
calm, information-dense, but never cluttered.

## Contents

- [Screenshots](#screenshots)
- [Features](#features)
- [Tech stack](#tech-stack)
- [Getting started](#getting-started)
- [Deployment](#deployment)
- [Data layer](#data-layer)
- [Project structure](#project-structure)
- [Design system](#design-system)
- [License](#license)

## Screenshots

<table>
<tr>
<td width="50%"><img src="./docs/screenshots/dashboard.png" alt="DockYard dashboard — stat cards, recent transactions, top moving products" width="100%" /><p align="center"><sub>Dashboard</sub></p></td>
<td width="50%"><img src="./docs/screenshots/products.png" alt="DockYard products table — search, filters, status badges" width="100%" /><p align="center"><sub>Products</sub></p></td>
</tr>
</table>

## Features

| Module | Purpose |
|---|---|
| 📊 **Dashboard** | Operational overview — total products, inventory value (with a real 7-day delta), low-stock items, recent transactions, warehouse summary, top movers. No vanity metrics. |
| 📦 **Products** | The product catalog — name, SKU, category, cost/selling price, quantity, reorder threshold, description, image. Deep-linkable filters (`?status=low-stock`). |
| 🔁 **Inventory** | Every stock movement: stock in, stock out, adjustments, transfers between warehouses — fully tracked. |
| 🚚 **Suppliers** | Supplier directory with contact person, email, phone, and address. |
| 🏭 **Warehouses** | Warehouse records — name, location, capacity, manager, live utilization. |
| 📈 **Analytics** | Inventory value trends, product distribution, stock movement trends, and low-stock reports as simple, actionable charts. |

Every table supports search, sort, filters, pagination, bulk actions, and
keyboard navigation, with a consistent **In Stock / Low Stock / Out of Stock**
status model throughout. A public [landing page](#screenshots) at `/`
showcases the real, live app — not mockups — before sending visitors into
the dashboard at `/app`.

## Tech stack

**Frontend** — React 19 · TypeScript · Vite · Tailwind CSS v4 · shadcn-style components on Radix primitives · React Router · TanStack Query · TanStack Table · React Hook Form · Zod · Recharts · Lucide icons · Figtree (self-hosted)

**Backend (target)** — Supabase (PostgreSQL, Auth, Row Level Security, Storage)

**Deployment** — Vercel · **Package manager** — pnpm

## Getting started

```bash
pnpm install
pnpm dev       # start the dev server
pnpm build     # type-check + production build
pnpm preview   # preview the production build
```

## Contributing

Contributions of every size are welcome, from fixing a typo to building a feature, and no experience is required. Issues labelled [**good first issue**](https://github.com/rohithprem18/dockyard/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22) are picked to be a friendly start.

<p>
  <a href="https://github.com/rohithprem18/dockyard/actions/workflows/ci.yml"><img src="https://img.shields.io/github/actions/workflow/status/rohithprem18/dockyard/ci.yml?style=flat-square&label=CI" alt="CI status"></a>
  <a href="https://github.com/rohithprem18/.github/blob/main/CONTRIBUTING.md"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square" alt="PRs welcome"></a>
  <a href="https://github.com/rohithprem18/dockyard/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22"><img src="https://img.shields.io/github/issues/rohithprem18/dockyard/good%20first%20issue?style=flat-square&label=good%20first%20issues&color=7057ff" alt="Good first issues"></a>
  <a href="#contributors"><img src="https://img.shields.io/github/contributors/rohithprem18/dockyard?style=flat-square&color=orange" alt="Contributors"></a>
</p>

1. **Pick an issue** (or open one with your idea) and comment that you're working on it.
2. **Fork** the repository and create a branch: `git checkout -b fix/short-description`.
3. **Make your change** and run the same checks as CI (see [`.github/workflows/ci.yml`](.github/workflows/ci.yml)).
4. **Open a pull request.** When every check passes, it is **merged automatically** and you appear under [Contributors](#contributors).

Changes to workflows, dependencies or deployment config wait for a maintainer review. See the [contributing guide](https://github.com/rohithprem18/.github/blob/main/CONTRIBUTING.md) and the [Code of Conduct](https://github.com/rohithprem18/.github/blob/main/CODE_OF_CONDUCT.md).

## Contributors

Thanks to everyone who has helped build this project!

<!-- CONTRIBUTORS:START -->
<!-- CONTRIBUTORS:END -->

## License

Distributed under the MIT License. See [LICENSE](LICENSE) for details.
