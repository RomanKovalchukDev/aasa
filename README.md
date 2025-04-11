# AASA Test Website

This is a simple website for testing Apple App Site Association (AASA) route exclusion on GitHub Pages.

## Setup

1. Fork this repository
2. Enable GitHub Pages in your repository settings
3. Update the AASA file with your actual Team ID and Bundle ID
4. Deploy the website

## Testing

The website includes two test routes:
- `/regular` - This route should be handled by your app
- `/excluded/test` - This route should NOT be handled by your app

## AASA Configuration

The `.well-known/apple-app-site-association` file contains the following configuration:
```json
{
    "applinks": {
        "apps": [],
        "details": [
            {
                "appID": "TEAMID.com.example.app",
                "paths": ["*", "!/excluded/*"]
            }
        ]
    }
}
```

Replace `TEAMID.com.example.app` with your actual Team ID and Bundle ID.

## Notes

- Make sure your AASA file is served with the correct MIME type: `application/json`
- The AASA file should be accessible at `https://your-username.github.io/.well-known/apple-app-site-association`
- Test the routes using an iOS device with your app installed 