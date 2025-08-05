# 💪 Claude Workouts - Gym Tracker App

A mobile-first web application for tracking gym workouts with GitHub integration for data persistence. Built for real gym use with large touch controls, automatic timers, and offline-first design. You can use this version as is, paired with your own workout data (see **Data Repository**), at https://bbendick.github.io/claude-workouts/.

## Features

- **3-Day Workout Program**: Upper Body, Lower Body, and Balance focused routines
- **Rep-by-Rep Tracking**: Tap to complete each rep with visual feedback
- **Automatic Timers**: 60-second rest periods and duration-based exercises (planks, wall sits)
- **Progress Tracking**: Complete workout history with timestamps
- **Weight Management**: Track and update resistance/weight per exercise
- **Mobile Optimized**: Large 80px touch targets perfect for gym use
- **GitHub Integration**: Persistent data storage using GitHub API
- **Offline Ready**: Works without internet, syncs when connected

## Why GitHub for Data Storage?

This app uses GitHub repositories for workout data storage for several key reasons:

1. **Free & Reliable**: GitHub provides free, reliable cloud storage with excellent uptime
2. **Version Control**: Complete history of all workout changes and progress
3. **Data Ownership**: You own your data in your own repository
4. **Cross-Device Sync**: Access your workouts from any device with internet
5. **Backup Built-in**: Your workout data is automatically backed up and versioned
6. **No Database Required**: Simple JSON files store all workout configurations and history
7. **Privacy**: Your workout data stays in your private repository

### Required Repositories

You'll need two GitHub repositories:

1. **Hosting Repository**: For the app itself (can be `username.github.io/claude-workouts`)
2. **Data Repository**: For storing workout data (e.g., `claude-workouts-data`)

The app stores:
- `workouts.json` - Exercise definitions and workout configurations
- `workouts-completed.json` - Complete workout session history

## Setup

### 1. GitHub Setup

1. Create a GitHub Personal Access Token with `repo` permissions
2. Create a repository for your workout data
3. Optionally, host the app on GitHub Pages

### 2. App Configuration

1. Open the app and click the ⚙️ settings button
2. Enter your GitHub credentials:
   - **GitHub Username**: Your GitHub username
   - **Repository Name**: Name of your data repository
   - **Personal Access Token**: Token with repo permissions
3. Click "Connect to GitHub"

## Local Development & Testing

For local development and testing, you can run the app using Python's built-in HTTP server:

```bash
# Navigate to the project directory
cd claude-workouts

# Start local server (Python 3)
python3 -m http.server 8000

# Or with Python 2
python -m SimpleHTTPServer 8000
```

Then open your browser to `http://localhost:8000`

### Development vs Production Mode

The app automatically detects the environment:

- **Development Mode** (`localhost` or `127.0.0.1`): Uses mock data for testing
- **Production Mode** (any other hostname): Uses real GitHub API calls

This allows you to:
- Test the app locally without GitHub setup
- Develop new features with mock data
- Deploy to production with real data persistence

## Data Structure

The app uses a normalized data structure to eliminate duplication:

```json
{
  "exercises": {
    "chest-press": {
      "name": "Chest Press (machine)",
      "muscleGroups": ["chest", "triceps", "shoulders"],
      "defaultSets": 3,
      "defaultTargetReps": 15,
      "currentWeight": 45
    }
  },
  "workouts": {
    "day1-upper": {
      "name": "Day 1: Upper Body Focus",
      "exercises": [
        {"exerciseId": "chest-press", "sets": 3, "targetReps": 15}
      ]
    }
  }
}
```

This structure allows:
- Single source of truth for each exercise
- Easy weight/note updates across all workouts
- Flexible per-workout overrides when needed

## Usage

1. **Select Workout Day**: Choose from Upper Body, Lower Body, or Balance
2. **Pick Exercise**: Tap any exercise to start
3. **Complete Sets**: Use large buttons to mark sets complete
4. **Rest Timer**: Automatic 60-second rest between sets
5. **Save Progress**: Save individual exercises or complete full day
6. **Track History**: View last workout and complete session history

## Technical Details

- **Single HTML File**: No build process, pure vanilla JavaScript
- **No Dependencies**: Works entirely in the browser
- **PWA Ready**: Can be installed as a mobile app
- **Responsive Design**: Adapts to various screen sizes
- **CORS Friendly**: Works when hosted on GitHub Pages

## Browser Requirements

- Modern browser with ES6 support
- JavaScript enabled
- Internet connection for GitHub sync (offline mode available)

## Privacy & Security

- All data stored in your private GitHub repository
- Personal Access Token stored only in browser session storage
- No third-party analytics or tracking
- Complete data ownership and control

## Contributing

This is a personal fitness tracking app, but feel free to fork and customize for your own workout routines!

## License

This project is open source. Feel free to use and modify for your personal fitness tracking needs.
