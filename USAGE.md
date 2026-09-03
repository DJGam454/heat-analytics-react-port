# Using Heat Analytics

## Start

Run `npm install`, then `npm run dev`. Open the local URL shown by Vite, usually `http://localhost:5173`.

## Strava activity

1. Open the activity in Strava.
2. Open the activity menu (`...`) and choose **Export GPX**.
3. Upload the downloaded `.gpx` file to Heat Analytics.

The track is parsed and analyzed in your browser. No GPX data is uploaded by the client-side dashboard.

## Hydration data

Enter pre-run weight, post-run weight, and fluid consumed to show hydration metrics. Urine output, carbs, sodium, recovery heart rate, and RPE are optional.

## Metric guide

- **HR drift:** average heart-rate change between the first and second halves.
- **Aerobic decoupling:** change in pace efficiency between halves.
- **Drift onset:** first 30-point rolling average above the 5% baseline threshold.
- **Sweat and intake rates:** values normalized to moving time.

## Deploy

Run `npm run build` to create `dist`, or connect the repository to Vercel. Vercel detects Vite automatically.
