# Otaku's Library Companion

A Flutter companion app for the **Otaku's Library** website. Browse, track, and curate your favorite anime, manga, manhwa, manhua, donghua, webcomics, and webnovels — all in one place.

## Features

### Content Discovery
- Browse content across **7 categories**: anime, manga, manhwa, manhua, donghua, webcomics, webnovels
- Search with smart category detection
- Content detail pages with ratings, stats, and community data
- Trending section, picks, and categories on the home screen

### Personal Library
- Add content to your library with custom status labels (Viewed, Current, Planned, Awaiting, Delayed, Dropped)
- Grid view with user-controlled column count (1–4 columns)
- Orientation-aware layout (portrait / landscape)
- Status icon badges on content cards
- Content stats with donut chart breakdown

### Community

- **TWIST** — Curate and share personal lists of favorites, grouped by category. Browse other community members' curated picks.
- **Guild** — Community hub with feed and discussions
- **Reviews** — Rate and review content
- **User profiles** — View stats, badges, followers, activity
- **Leaderboards** — Community stats with status-based breakdowns
- **Reports** — Report problematic content or users

### App Experience
- Material 3 design with custom theming
- Animated wave transition between dark and light modes
- Custom floating navigation bar (portrait) / sidebar (landscape)
- Frosted glass effects throughout
- Full Supabase auth (email/password, Google OAuth, browser session)

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | Flutter (Material 3) |
| State Management | Riverpod |
| Backend / Auth | Supabase |
| Routing | GoRouter |
| Images | CachedNetworkImage |
| Icons | Flutter Material Icons |
| Typography | Raleway |

## Getting Started

### Prerequisites
- Flutter SDK (latest stable)
- Android Studio or VS Code with Flutter extensions
- A Supabase project (for backend)

### Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/otakucompanion.git
cd otakucompanion

# Install dependencies
flutter pub get

# Set up environment variables
# Create a .env file in the project root with:
# SUPABASE_URL=your_supabase_url
# SUPABASE_ANON_KEY=your_supabase_anon_key

# Run the app
flutter run
```

### Configuration

The app requires a Supabase instance with the following tables configured:
- `Ani_data`, `Manga_data`, `Manhwa_data`, `Manhua_data`, `Comic_data`, `Donghua_data`, `Webnovel_data`
- `user_data`, `user_stats`, `user_lists`, `user_badges`
- `trending`, `reviews`, `notifications`, `follows`
- `library_cache`, `content_suggestions`, `subscriptions`

## Project Structure

```
lib/
├── app.dart                  # App root with animated theme transition
├── main.dart                 # Entry point
├── core/
│   ├── router/               # GoRouter configuration
│   ├── supabase/             # Supabase initialization
│   ├── services/             # Core services (heartbeat, etc.)
│   └── theme/                # Theme system (colors, spacing, typography)
├── features/
│   ├── auth/                 # Sign-in, sign-up, session management
│   └── home/
│       ├── models/           # Data models
│       ├── providers/        # Riverpod providers
│       ├── screens/          # Screen widgets
│       ├── services/         # API service classes
│       └── widgets/          # Reusable widget components
└── shared/
    └── widgets/              # Shared widgets (nav bar, search, etc.)
```

## Platform Support

| Platform | Status |
|----------|--------|
| Android  | ✅ Primary target |
| Windows  | ✅ Supported (some features limited) |
| iOS      | ❌ Not supported (no Apple developer account) |
| Web      | ❌ Not supported |
