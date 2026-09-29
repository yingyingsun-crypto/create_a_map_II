# DC Park // 04%

A low-power Washington, DC park map designed for a visitor whose phone has only 4% battery remaining.

Live site: <https://dc-park-04-terminal.esun6037.chatgpt.site/>

## Features

- Displays DC Department of Parks and Recreation park boundaries.
- Displays National Park Service parks, memorials, and historic sites.
- Searches park names, addresses, wards, and site types.
- Filters recorded human drinking-water facilities. Lakes, ponds, and rivers are excluded.
- Requests browser location permission only when the user selects the location control.
- Finds the nearest recorded DC-managed park and provides a Google Maps directions link.
- Shows verified Rock Creek Park visitor information, drinking water, restrooms, visitor centers, and operating-hour guidance.
- Clearly labels phone-charging information as unverified when no reliable source exists.

## Run locally

This is a static site with no build step. Run a local web server from the repository root:

```bash
python3 -m http.server 8000 --directory dist
```

Then open <http://localhost:8000>.

Do not open `index.html` directly from the file system because browsers may block local GeoJSON requests. Browser geolocation normally requires HTTPS, with `localhost` commonly treated as a development exception.

## GitHub Pages

### Publish from the repository root

Copy the contents of `dist/` to the repository root so that `index.html`, `data/`, and `vendor/` are at the top level. Then select:

- **Settings → Pages**
- **Source:** Deploy from a branch
- **Branch:** `main`
- **Folder:** `/(root)`

### Publish with GitHub Actions

The source repository also includes `.github/workflows/pages.yml`. To use it, keep the website inside `dist/` and select **GitHub Actions** as the Pages source.

## Source repository structure

```text
.
├── .github/workflows/pages.yml
├── dist/
│   ├── index.html
│   ├── data/
│   │   ├── parks.geojson
│   │   ├── nps.json
│   │   └── nps-facilities.json
│   └── vendor/leaflet/
├── DATA_SOURCES.md
└── README.md
```

## Privacy and limitations

- Location is requested only after the user selects the location button. The site code does not store or transmit the location.
- Drinking-water counts come from public-data snapshots and do not guarantee that a fountain is currently operating.
- NPS representative points are not complete park boundaries.
- No reliable citywide public phone-charging dataset is available, so estimated locations are never presented as confirmed charging points.
- See [DATA_SOURCES.md](DATA_SOURCES.md) for source and coverage details.

## Technology

Vanilla HTML, CSS, JavaScript, Leaflet, OpenStreetMap tiles, and the browser Geolocation API.

## License note

No open-source license has been selected for this repository. Choose an appropriate license before distributing the code as an open-source project. Third-party libraries, map tiles, and public datasets remain subject to their respective terms and attribution requirements.
