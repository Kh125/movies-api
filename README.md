# Movies API (Laravel + TMDB)

This project is a Laravel application that fetches movie and actor data from [The Movie Database (TMDB)](https://www.themoviedb.org/) and serves pages for:

- Popular movies
- Now playing movies
- Movie details
- Popular actors
- Actor details
- Live movie search (Livewire component)

> Note: Despite the repository name, this is currently a server-rendered Laravel app that consumes the TMDB API.

## Tech Stack

- PHP / Laravel 8
- Livewire
- Spatie View Models
- Tailwind CSS + Laravel Mix
- PHPUnit

## Requirements

- PHP `^7.3|^8.0` (use PHP 8.1 or lower for the current lockfile)
- Composer
- Node.js + npm
- TMDB API read access token

## Setup

1. Clone the repository.
2. Install PHP dependencies:

   ```bash
   composer install
   ```

3. Install JavaScript dependencies:

   ```bash
   npm install
   ```

4. Create a `.env` file in the project root (if missing), set your app settings, and add:

   ```env
   TMDB_TOKEN=your_tmdb_read_access_token
   ```

5. Generate an app key:

   ```bash
   php artisan key:generate
   ```

6. Start the application:

   ```bash
   php artisan serve
   ```

## Available Routes

- `/` → Movies index (popular + now playing)
- `/movies/{movie}` → Movie details
- `/actors` → Popular actors
- `/actors/page/{page?}` → Paginated actors list
- `/actors/{actor}` → Actor details

## Frontend Build

Development build:

```bash
npm run dev
```

Production build:

```bash
npm run production
```

## Running Tests

```bash
php artisan test
```

## Deployment

The repository includes a `Procfile` for Heroku-style deployment:

```procfile
web: vendor/bin/heroku-php-apache2 public/
```
