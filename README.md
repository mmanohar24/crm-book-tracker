# CRM-Inspired Book Tracker App

A full-stack React application for managing a personal reading list with complete CRUD functionality. Built with a CRM-style data flow — centralized state management via React Context API, persistent storage through a REST API backend, and clean component separation for create, read, update, and delete operations.

## Features

- Add new books to your reading list
- Edit book titles inline
- Delete books from the list
- Fetches and persists data through a REST API (json-server)
- Global state managed with React Context API and `useCallback` for optimized re-renders

## Tech Stack

- **Frontend:** React, Axios, Context API
- **Backend:** json-server (REST API)
- **State Management:** React Context + useState + useCallback
- **HTTP Client:** Axios

## Project Structure

```
src/
├── components/
│   ├── BookCreate.js       # Form to add a new book
│   ├── BookEdit.js         # Inline edit form
│   ├── BookList.js         # Renders the list of books
│   └── BookShow.js         # Individual book card with edit/delete
├── context/
│   └── books.js            # Context provider with all CRUD operations
├── hooks/
│   └── use-books-context.js
├── App.js
└── index.js
```

## Getting Started

### Prerequisites

- Node.js (v16+)
- npm

### Installation

```bash
# Install dependencies
npm install

# Start the JSON server (backend) on port 3001
npx json-server --watch db.json --port 3001

# In a separate terminal, start the React app
npm start
```

The app runs at `http://localhost:3000` and the API at `http://localhost:3001/books`.

## API Endpoints

| Method | Endpoint     | Description       |
|--------|--------------|-------------------|
| GET    | /books       | Fetch all books   |
| POST   | /books       | Create a new book |
| PUT    | /books/:id   | Update a book     |
| DELETE | /books/:id   | Delete a book     |

## Key Concepts Demonstrated

- **Context API** for app-wide state without prop drilling
- **useCallback** to prevent unnecessary re-renders on context consumers
- **Async/await** with Axios for all API operations
- **Optimistic UI updates** — local state is updated immediately after each API response
- **Component composition** — each CRUD operation lives in its own focused component
