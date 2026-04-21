# Book Tracker App

A reading list manager built with React. You can add, edit, and delete books — changes go straight to a json-server backend via axios, and Context API keeps everything in sync across the app.

## Features

- Add books to your reading list
- Edit titles inline without leaving the page
- Delete books instantly
- All changes persist through a local REST API

## Stack

- React + Context API
- json-server (local REST backend)
- Axios

## Setup

```bash
npm install

# Start the backend (runs on port 3001)
npx json-server --watch db.json --port 3001

# Start the app (in a new terminal)
npm start
```

App is at `http://localhost:3000`. The API runs at `http://localhost:3001/books`.

## Endpoints

| Method | Endpoint     | Description       |
|--------|--------------|-------------------|
| GET    | /books       | Fetch all books   |
| POST   | /books       | Add a book        |
| PUT    | /books/:id   | Update a book     |
| DELETE | /books/:id   | Remove a book     |

## What I worked on

- Context API to share state across components without prop drilling
- useCallback to avoid unnecessary re-renders when the context updates
- async/await with axios for every API call
- Each CRUD operation is its own component, so the code stays easy to follow
