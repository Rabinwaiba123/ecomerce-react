# CodeBook

CodeBook is a React-based eBook storefront for computer science readers. It lets visitors browse products, view product details, search the catalog, manage a cart, and place orders after signing in. The app also includes a dashboard for authenticated users and a dark mode toggle for the main interface.

## Features

- Product browsing with featured products and detailed product pages
- Search across the catalog
- User registration and login
- Protected cart, order summary, and dashboard routes
- Cart state and order creation for authenticated users
- Dark mode preference stored in the browser
- Responsive layout with shared header, footer, and reusable UI components

## Tech Stack

- React 18
- React Router v6
- Tailwind CSS
- json-server and json-server-auth for the local API
- react-toastify for notifications

## Project Structure

- `src/pages` contains the routed pages for home, products, auth, cart, orders, and dashboard
- `src/components` contains shared layout and UI components
- `src/context` and `src/reducers` manage cart and filter state
- `src/services` contains the API calls for products, auth, and user orders
- `data/db.json` provides the mock backend data used by json-server

## Getting Started

### Prerequisites

- Node.js 16+ recommended
- npm

### Install Dependencies

```bash
npm install
```

### Configure the API Host

The app reads its backend URL from `REACT_APP_HOST`. Create a `.env` file in the project root and point it to your local JSON server or API gateway.

```bash
REACT_APP_HOST=http://localhost:5000
```

### Start the Frontend

```bash
npm start
```

The app runs at `http://localhost:3000`.

### Start the Mock Backend

This project expects a json-server-auth backend backed by `data/db.json`. One common local setup is:

```bash
npx json-server-auth --watch data/db.json --port 5000
```

If you already have an API service running elsewhere, just update `REACT_APP_HOST` to match it.

### Build for Production

```bash
npm run build
```

## Available Scripts

- `npm start` runs the app in development mode
- `npm test` starts the test runner
- `npm run build` creates an optimized production build
- `npm run eject` exposes the underlying Create React App configuration

## Routing Overview

- `/` home page
- `/products` product listing
- `/products/:id` product details
- `/login` sign in
- `/register` sign up
- `/cart` protected cart page
- `/order-summary` protected order summary page
- `/dashboard` protected user dashboard

## Deployment

The repo includes a `netlify.toml` redirect so client-side routes can be refreshed directly in production. For static hosting, deploy the built `build` folder after setting `REACT_APP_HOST` to your production API.

## Notes

- Authentication state is stored in `sessionStorage`
- Dark mode is stored in `localStorage`
- Mock product and order data live under `data/`
