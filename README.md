# Haven App Deep Links

A Node.js/Express web service that handles deep links for the Haven App, providing seamless app-to-web integration and fallback options for mobile users.

## Overview

This service runs at `app.havenbibleapp.com` and handles deep linking for the Haven App:

- **Custom URL Scheme**: `havenapp://`
- **iOS App Store ID**: `6503387382`
- **Android Package**: `com.vertmedia.haven`

## Features

- ✅ Universal deep link handling for all app routes
- ✅ Automatic platform detection (iOS/Android)
- ✅ Intelligent app store fallbacks
- ✅ Mobile-optimized, responsive design
- ✅ Loading animations and user feedback
- ✅ Error handling and edge case management
- ✅ Heroku deployment ready

## How It Works

1. **URL Access**: User visits any URL like `app.havenbibleapp.com/verse/john-3-16`
2. **Deep Link Attempt**: JavaScript immediately tries to open `havenapp://verse/john-3-16`
3. **Platform Detection**: Detects iOS/Android for optimized handling
4. **App Store Fallback**: If app isn't installed, redirects to appropriate app store after 2-second delay
5. **Manual Options**: Shows app store buttons as final fallback

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd haven-links
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm start
```

4. Visit `http://localhost:3000` to test locally

## Deployment

### Heroku Deployment

1. Create a new Heroku app:
```bash
heroku create your-app-name
```

2. Set up your custom domain:
```bash
heroku domains:add app.havenbibleapp.com
```

3. Deploy:
```bash
git add .
git commit -m "Initial commit"
git push heroku main
```

### Environment Variables

The app automatically uses `process.env.PORT` for Heroku deployment. No additional environment variables are required.

## File Structure

```
haven-links/
├── server.js          # Express server
├── public/
│   └── index.html     # Deep link handler page
├── package.json       # Dependencies and scripts
├── Procfile          # Heroku deployment config
├── .gitignore        # Git ignore rules
└── README.md         # This file
```

## Deep Link Examples

- `app.havenbibleapp.com/` → `havenapp://`
- `app.havenbibleapp.com/verse/john-3-16` → `havenapp://verse/john-3-16`
- `app.havenbibleapp.com/chapter/genesis-1` → `havenapp://chapter/genesis-1`
- `app.havenbibleapp.com/search?q=love` → `havenapp://search?q=love`

## Browser Support

- ✅ Safari (iOS)
- ✅ Chrome (Android/Desktop)
- ✅ Firefox
- ✅ Edge
- ✅ Mobile browsers

## Technical Details

### Deep Link Strategies

- **iOS**: Direct scheme handling with fallback detection
- **Android**: Intent URLs with Play Store fallback
- **Desktop**: Basic scheme attempt with manual options

### Error Handling

- Network connectivity issues
- App not installed scenarios
- Unsupported browsers
- Invalid deep link formats

## Development

### Local Testing

1. Start the server: `npm start`
2. Visit `http://localhost:3000/test/path`
3. Check browser console for deep link attempts
4. Test on actual mobile devices for full functionality

### Debugging

The page includes comprehensive console logging for debugging deep link behavior:

- Deep link URL generation
- Platform detection results
- App launch attempts
- Fallback triggers

## License

MIT License - see LICENSE file for details.

## Support

For technical support or feature requests, please contact the Haven App development team.