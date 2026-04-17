# Life OS Dashboard - Specification

## Project Overview
- **Project Name**: Life OS
- **Type**: Single-page web dashboard
- **Core Functionality**: A hyper-aesthetic personal dashboard combining productivity tools with ambient weather-responsive theming
- **Target Users**: Anyone wanting a cozy, inspiring digital workspace

## UI/UX Specification

### Layout Structure
- **Container**: Full viewport, centered content with max-width 1200px
- **Grid**: CSS Grid with 3 main panels (left sidebar, main content, right sidebar)
- **Responsive**: Mobile-first, stacks vertically on screens < 768px

### Visual Design

#### Color Palette (Default - Rainy Kyoto)
- **Background**: `#1a1a2e` (deep night blue)
- **Glass Surface**: `rgba(255, 255, 255, 0.08)` with backdrop-blur
- **Primary Accent**: `#e0aaff` (soft lavender)
- **Secondary Accent**: `#c8b6ff` (pale purple)
- **Text Primary**: `#e8e8e8`
- **Text Secondary**: `#a0a0a0`
- **Rain Effect**: `rgba(174, 194, 224, 0.3)`

#### Typography
- **Font Family**: "IBM Plex Mono" for retro terminal feel, "Outfit" for modern headings
- **Headings**: 24px-32px, weight 600
- **Body**: 14px-16px, weight 400
- **Mono elements**: 13px for terminal-style text

#### Visual Effects
- **Glassmorphism**: backdrop-filter: blur(20px), rgba backgrounds, subtle borders
- **Rain Animation**: CSS keyframe raindrops falling
- **Glow Effects**: Soft box-shadows with accent colors
- **Transitions**: 0.3s ease for all interactive elements

### Components

#### 1. Weather Widget (Top Right)
- Shows current weather with animated icon
- Temperature in both °C and °F
- Changes entire dashboard theme based on weather:
  - Sunny: Warm amber tones (#ffb347, #ffcc33)
  - Rainy: Cool blue/purple tones (default)
  - Cloudy: Muted gray tones (#7a7a8c, #5a5a6e)
  - Night: Deep indigo tones (#2d1b69, #1a1a3e)

#### 2. To-Do List (Main Panel)
- Add new tasks with input field
- Tasks display with checkbox, text, and delete button
- Completed tasks get strikethrough and dimmed
- Task count display
- Category tags (work, personal, urgent)

#### 3. Clock/Time Display (Top Left)
- Large digital clock in retro LED style
- Date display with Japanese formatting option
- Greeting message based on time of day

#### 4. Quick Notes Panel (Right Sidebar)
- Simple text area for quick notes
- Auto-saves to localStorage
- Minimalist design

#### 5. Ambient Sound Toggle
- Play lo-fi rain/cafe sounds
- Mute/unmute button with icon

#### 6. Rain Effect Overlay
- Animated raindrops across the screen
- Toggle on/off
- Particle density adjustable

### Interactive Behaviors
- All data persists in localStorage
- Smooth hover states on all interactive elements
- Floating animation on main panels
- Keyboard support for task input (Enter to add)

## Functionality Specification

### Core Features
1. **To-Do List**
   - Add task (text input + Enter key or button)
   - Mark complete (checkbox toggle)
   - Delete task (X button)
   - Filter by category
   - Clear completed

2. **Weather Integration**
   - Fetch from Open-Meteo API (free, no API key)
   - Auto-detect location or manual city search
   - Theme updates based on weather condition

3. **Clock & Greeting**
   - Real-time clock update every second
   - Time-based greeting (Good morning/afternoon/evening/night)
   - Japanese date format option

4. **Notes**
   - Simple markdown-lite notes
   - Auto-save on type (debounced)

5. **Audio**
   - Lo-fi ambient rain sounds
   - Toggle with smooth fade

### Edge Cases
- Weather API failure: Show default theme with manual override option
- Empty states: Friendly placeholder text
- Long task text: Truncate with ellipsis

## Acceptance Criteria
- [ ] Dashboard loads with glassmorphism aesthetic
- [ ] Rain animation plays smoothly
- [ ] Weather fetches and applies theme
- [ ] Tasks can be added, completed, deleted
- [ ] Data persists after page refresh
- [ ] Responsive on mobile devices
- [ ] No console errors on load
