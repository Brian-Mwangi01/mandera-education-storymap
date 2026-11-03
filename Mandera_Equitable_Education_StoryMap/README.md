# Beyond School Locations — Mandera County StoryMap

A lightweight, static, mobile-friendly visual story built from exported GIS maps and charts. It does **not** use ArcGIS StoryMaps or require a GIS server.

## Preview locally

Open `index.html` in a modern browser. All images and styles are stored locally in this folder.

## Publish with GitHub Pages

1. Create a new **public** GitHub repository (for example `mandera-education-storymap`).
2. Upload all files and folders in this package. Make sure `index.html` is in the repository root.
3. In the repository, open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select branch `main` and folder `/ (root)`, then save.
6. GitHub will provide a public Pages URL after deployment. Open it and test the page on desktop and mobile.

No build step, API key, ArcGIS account or external map service is required.

## Notes on the data

- The school-count chart contains an unresolved source category shown as `?1` (6 mapped schools). It is deliberately not renamed without source verification.
- The digital-devices chart is calculated from ICT Authority DigiSchool learner-device and school totals by Mandera reporting unit.
- Elimu Yetu electricity, internet, device receipt and utilization percentages are shown separately as pooled ten-county context, not Mandera-specific measurements.
- Nearest-school distances are straight-line centroid-to-school distances, not walking distance or travel time.
