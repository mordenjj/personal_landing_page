# Personal Landing Page

## Overview
A simple static HTML landing page for Digital Product Management.

## Project Structure
- `index.html` - Main landing page (the entire app)
- `.github/workflows/` - Azure Static Web Apps CI/CD pipeline (not used on Replit)

## Running the App
The app is served using Python's built-in HTTP server:
```
python3 -m http.server 5000 --bind 0.0.0.0
```
Runs on port 5000.

## Deployment
Configured as a static site deployment with the root directory (`.`) as the public directory.
