# MovieLibrary — Watch List

A web-programming coursework application for keeping track of watched movies and series. A React interface communicates with a PHP JSON API backed by MySQL.

## Project background

I built this watch-list application for a university web programming course.

**Previous repository name:** `PWEB_Ujian`.

## What it does

Lists, adds, edits, and deletes watch-list entries. Each entry records a title, episode or season, genre, and last-watched date. The frontend provides a form dialog and refreshes the list after changes.

**Stack:** React · JavaScript · PHP / MySQLi · MySQL · Tailwind CSS

## Project map

| Path | Purpose |
|---|---|
| [frontend/project/](frontend/project/) | Actual React application and npm scripts |
| [frontend/project/src/api.js](frontend/project/src/api.js) | API calls; defaults to `http://localhost:8000` |
| [backend/index.php](backend/index.php) | GET, POST, PUT, and DELETE handlers |
| [backend/db.php](backend/db.php) | MySQL connection settings |
| [movielibrary.sql](movielibrary.sql) | Database schema and sample records |

The root and `frontend/` also contain package manifests, but the application startup commands belong to **`frontend/project/`**.

## Run locally

Install PHP with the MySQLi extension, a local MySQL-compatible database, and Node.js/npm compatible with the supplied React toolchain.

```sh
git clone https://github.com/mrafi-aditya/movielibrary-watchlist.git
cd movielibrary-watchlist
```

1. Start the local database service, for example MySQL in XAMPP.
2. Import `movielibrary.sql` into a local development database. Align its name with `backend/db.php`. The API queries the **`movies`** table, not `movie`.
3. From the repository root, start the API:

   ```sh
   php -S localhost:8000 -t backend
   ```

4. In another terminal, start React:

   ```sh
   cd frontend/project
   npm install
   npm start
   ```

Open `http://localhost:3000`. If using another API address, update the `API_URL` constant in `frontend/project/src/api.js`. `web-vitals` is already listed in the frontend dependencies; install from that directory rather than the repository root.

## API surface and scope

`GET` lists entries or reads an `id` query parameter. `POST`, `PUT`, and `DELETE` read JSON request bodies; updates and deletes require an `id`. This is a local CRUD coursework prototype with no account system or production deployment claimed here. The current API uses permissive CORS and needs further validation and error handling before public hosting.
