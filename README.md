# Heat Analytics React Port

A Vite + React port of the Heat Analytics Streamlit dashboard. Upload a GPX run to calculate distance, pace, elapsed and moving time, heart-rate statistics, HR drift, aerobic decoupling, HR stability, drift onset, and optional hydration and fueling metrics.

## Local development

```bash
npm install
npm run dev
```

Open the local URL printed by Vite, normally `http://localhost:5173`.

## Production build

```bash
npm run lint
npm run build
npm run preview
```

## Deploy to Vercel

Import this repository into Vercel and use the default Vite settings:

- Build command: `npm run build`
- Output directory: `dist`
- Install command: `npm install`

The dashboard works without environment variables. Weather history can be added through a serverless `/api/weather` endpoint using `WEATHER_API_KEY`; the interface intentionally degrades gracefully when weather is unavailable.

## Port behavior

The browser implementation preserves the original rules: geodesic-style GPS distance using the haversine approximation, removal of speeds above 30 kph, moving threshold above 1 kph, midpoint-based cardiovascular calculations, a 30-point rolling HR drift threshold of 5%, and whole-body sweat-loss accounting.

No GPX files or database credentials are uploaded or stored by the client-only dashboard.

## Strava import

The GPX uploader accepts files exported directly from Strava. Open a Strava activity, choose the activity menu, select **Export GPX**, then upload the downloaded file. Analysis runs locally with the same GPX pipeline. Direct Strava account OAuth is not enabled because it requires a server-side Strava app client secret and callback configuration.

## Project structure

```text
src/App.jsx    Dashboard, GPX parser, cleaning, and metrics
src/App.css    Responsive visual design
src/index.css  Global styles and typography
```

See [USAGE.md](USAGE.md) for the complete user guide.

MIT licensed.
