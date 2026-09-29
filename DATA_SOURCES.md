# Data sources and limitations

The data supports the website experience but does not represent real-time facility status. Check the managing agency's website for current hours, closures, and on-site availability before visiting.

## DC parks

- Source: [DC Open Data — Parks and Recreation Areas](https://opendata.dc.gov/datasets/DCGIS::parks-and-recreation-areas)
- Website file: `dist/data/parks.geojson`
- Use: DC DPR park boundaries, names, addresses, wards, types, and selected facility counts.
- Drinking water: based on the dataset's `DRINKFOUNT` / “Drinking Fountain” field.
- Limitation: recorded counts do not guarantee that a facility is currently operating. The dataset does not provide a reliable public phone-charging field.

## National Park Service

- Source: [NPS Data API](https://www.nps.gov/subjects/developer/api-documentation.htm)
- Website file: `dist/data/nps.json`
- Use: names, types, descriptions, official pages, and representative locations for NPS units in Washington, DC.
- Limitation: representative points are not complete park boundaries. Base records do not include every drinking-water, restroom, or charging location.

## Rock Creek Park facilities

- Sources: [Rock Creek Park FAQ](https://www.nps.gov/rocr/faqs.htm), [Operating Hours](https://www.nps.gov/rocr/planyourvisit/hours.htm), [Nature Center & Planetarium](https://www.nps.gov/rocr/planyourvisit/nature-center-and-planetarium.htm), and [Peirce Mill](https://www.nps.gov/rocr/planyourvisit/peirce-mill-visitor-center.htm)
- Website file: `dist/data/nps-facilities.json`
- Use: operating-hour guidance, visitor centers, drinking water, and restrooms.
- Limitation: facility availability can change because of seasons, maintenance, and staffing. No public phone-charging location has been confirmed.

## Base map

- Map tiles: [OpenStreetMap](https://www.openstreetmap.org/)
- Map library: [Leaflet](https://leafletjs.com/)
- The website retains visible OpenStreetMap contributor attribution.

## Snapshot date

The interface labels the data snapshot as 2025–2026. When updating the project, verify this document, the `updated` or `retrieved` fields in the data files, and the data date shown in the site footer.
