# Claude Workouts Project Context

## Project Overview
A web-based gym workout tracking app that integrates with GitHub for data persistence. Built for mobile gym use with large touch controls, automatic timers, and offline-first design.

## Current Status
- ✅ **Working prototype** - hosted on GitHub Pages with GitHub API integration
- ✅ **Core functionality** - rep tracking, timers, workout progression
- ✅ **Development/Production modes** - mock data for local dev, real API for production
- 🔄 **Needs refinement** - UX improvements, better error handling, mobile optimization

## Technical Architecture

### Frontend
- **Single HTML file** with embedded CSS/JS
- **No external dependencies** - pure vanilla JavaScript
- **PWA-ready** with offline capabilities
- **Mobile-first design** with large touch targets

### Data Storage
- **GitHub API** for workout configuration and session history
- **JSON format** for all data
- **Personal Access Token** authentication
- **CORS-friendly** when hosted on GitHub Pages

### Development Setup
- **Local development**: Python HTTP server with mock data
- **Production**: GitHub Pages with real GitHub API calls
- **Auto-detection**: `isDevelopment` flag based on hostname

## Key Features

### Workout Tracking
- **3-day rotation**: Upper Body, Lower Body, Balance
- **Rep-by-rep tracking**: Tap to complete each rep
- **Automatic timers**: 60s rest + duration-based exercises (planks, wall sits)
- **Set progression**: Guided flow through sets and exercises
- **Session recording**: Complete workout history with timestamps

### Mobile Gym Optimization
- **Large buttons**: 80px touch targets for gym use
- **Clear timers**: Prominent countdown displays
- **Progress indicators**: Visual feedback on current set/exercise
- **One-handed operation**: Minimal interaction required during workouts

### Data Management
- **Persistent storage**: Survives browser sessions
- **Backup export**: JSON download capability
- **Weight tracking**: Configurable resistance/weight per exercise
- **Session history**: Complete workout log with dates

## Current Issues to Address
1. **Timer UX**: Make rest/exercise timers more prominent
2. **Navigation**: Improve back/forward flow between exercises
3. **Data validation**: Better error handling for API failures
4. **Mobile layout**: Optimize for various screen sizes
5. **Accessibility**: Add proper ARIA labels and keyboard navigation

## File Structure
```
claude-workouts/
├── index.html          # Main application
├── workouts.json       # Workout configuration
├── PROJECT_CONTEXT.md  # This file
└── README.md          # Setup instructions
```

## GitHub Configuration Required
- **Repository 1**: GitHub Pages hosting (username.github.io/repo-name)
- **Repository 2**: Data storage (claude-workouts)
- **Personal Access Token**: With 'repo' permissions for API access

## Development Workflow
1. **Local testing**: `python -m http.server 8000`
2. **Feature development**: Use mock data mode
3. **Production testing**: Deploy to GitHub Pages
4. **Data persistence**: Real GitHub API integration

## Next Development Priorities
1. **Mobile responsiveness** improvements
2. **Better timer UI/UX**
3. **Offline data sync** robustness
4. **Exercise customization** interface
5. **Progress tracking** and analytics

## User Context
- **Fitness level**: Beginner following structured 3-day program
- **Physical limitation**: Lower back condition (degenerative disk)
- **Usage pattern**: 3x/week gym sessions, evening/weekend
- **Technical comfort**: High - can handle JSON editing, GitHub setup
- **Primary goal**: Eliminate pre-workout friction, reliable data tracking