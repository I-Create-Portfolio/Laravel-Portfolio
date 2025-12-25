<!-- Copilot / AI agent instructions for contributors working on this repo -->
# Copilot instructions — Laravel Portfolio

Be concise. Aim for small, safe edits (fixes, tests, docs) unless asked to add large features.

Key project facts
- Laravel 10 app (PHP >= 8.1) with Livewire (v3.x) and Vite for frontend builds.
- Important folders: `app/Models` (Eloquent models), `app/Http/Controllers`, `app/Livewire` (Livewire components), `resources/views` (Blade), `resources/views/components` (Blade components), `routes/web.php`.
- Admin UI assets live under `public/admin` and compiled assets are built with Vite.

Developer workflows (exact commands discovered in this repo)
- Install PHP deps: `composer install`
- Install JS deps: `npm install`
- Dev frontend: `npm run dev` (Vite)
- Build frontend: `npm run build`
- DB setup: `php artisan migrate` (use `database/laravel_portfolio.sql` as a reference/dump)
- Run app: `php artisan serve`
- Real-time/chat: `php artisan reverb:start` (repo README references Laravel Reverb + Pusher)
- Queue worker: `php artisan queue:work`
- Tests: run PHPUnit with `./vendor/bin/phpunit` (phpunit.xml present)
- Lint/format: `./vendor/bin/pint` (laravel/pint is in composer.json)

Project-specific conventions and patterns
- Livewire components live in `app/Livewire` and are used in both admin and web pages (e.g., `AdminChatPage.php`, `WebChatPage.php`). Prefer small, single-responsibility Livewire components.
- Blade components are in `resources/views/components` (e.g., `blog-list.blade.php`). When editing views, prefer minimal markup changes and keep server-side logic in controllers/Livewire.
- Models live in `app/Models` and follow standard Eloquent conventions: see `Blog.php`, `Project.php`, `Settings.php` for patterns (timestamps, relationships, fillable/guarded).
- Authorization uses `spatie/laravel-permission` (check `config/permission.php` and middleware in `app/Http/Kernel.php`). When adding roles/permissions, follow existing seeds/migrations naming.

Integration & external dependencies to be mindful of
- Pusher / Laravel Reverb are used for realtime chat (see `.env` keys referenced in README). Avoid committing secrets; use `.env.example` as canonical template.
- Database seed/dumps: `database/laravel_portfolio.sql` exists — useful for reproducing production data shape.

Where to make safe edits
- Small bugfixes: update controller, model, or Livewire files; update corresponding view under `resources/views` or component.
- Assets/CSS/JS: change source in `resources/js`/`resources/css`, then use `npm run dev` to test.
- Migrations & seeders: add new migrations under `database/migrations` and seeders under `database/seeders` when schema changes are required.

Examples to reference when coding
- Livewire pages: `app/Livewire/AdminChatPage.php`, `app/Livewire/WebChatPage.php`
- Blog model and list view: `app/Models/Blog.php` + `resources/views/components/blog-list.blade.php`
- Routes: `routes/web.php` — check route groups for admin vs web middleware.

Acceptance notes for PRs
- Keep changes minimal and well-scoped. Include a short manual test in PR description (commands to run + page to visit).
- When adding env keys, update `.env.example` only.
- For DB changes include a migration and, when possible, a small seeder to validate behavior.

If unsure, ask the maintainer for context before large refactors. After creating or editing runnable code, prefer to run the fast checks: `composer install` (if deps changed), `npm run dev` (or `npm run build`) and `./vendor/bin/phpunit`.

End of instructions.
