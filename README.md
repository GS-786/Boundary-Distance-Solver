# Site Plan Solver

Read site coordinates from a PDF, Excel/CSV, image or manual entry. See the boundary drawn with every distance, bearing and area, measure on screen with CAD-style snaps, issue a title-block layout sheet to CAD, map the surroundings, and set out boreholes and tests.

(Formerly Boundary Distance Solver.)

**Live:** https://gs-786.github.io/Site-Plan-Solver/

## Tabs

| Tab | What it does |
| --- | --- |
| **B-01 Coordinates** | Import a PDF schedule (text layer, or OCR if scanned), Excel/CSV, a photo or screenshot (OCR), or pasted text. OCR removes table grid lines first and reads thin CAD fonts; Arabic-Indic digits (٠١٢٣٤٥٦٧٨٩, with ٫ or comma decimals) are read by a built-in digit matcher, so check those digits before importing. Review the columns it found, then replace or append. Edit points by hand. |
| **B-02 Boundary** | Zoomable plan with edge distances, bearings, point IDs, coordinates and area. Hover a corner or edge for details. |
| **B-03 Distances** | Every edge with ΔE, ΔN, distance, bearing, ground distance (scale factor) and slope/grade when levels exist. Point-to-point calculator and distance matrix. |
| **B-04 Measure** | Distance, path, area, angle and square offset to the boundary. Snaps to corners, midpoints, edges, perpendiculars and earlier measurements; Shift for ortho. Load a PDF page or image as an underlay and calibrate it by drawing scale, a known distance, or two known coordinates. |
| **B-05 Layout** | A drawing sheet (A4 to A0, landscape or portrait, auto or fixed scale) with coordinate grid, dimensioned boundary, north arrow, scale bar, coordinate and distance schedules and area, inside the MSCEB A1 title sheet (logo, project, client, notes, key plan, revisions, sheet title, signatures, stage and sheet number). Smaller sheets use the same title block at reduced size. Notes are printed in capitals in standard survey-drawing wording. Optional surroundings (roads, buildings and facilities) in the drawing, and a key plan in the title block. Export it as DXF, SVG or print it to PDF. |
| **B-06 Surroundings** | The site on a map (streets, OpenStreetMap, light grey or satellite, with street names) and the plot corners labelled P1, P2…. **Find nearby** loads the facilities (healthcare, education, places of worship, government and emergency, transport and fuel, shopping, food, banks, parks and sport, hotels, utilities), roads and buildings within 250 m to 5 km, with the distance from the boundary and direction of each, the nearest of every kind, and the roads next to the site. Every facility links to Google Maps and directions from the site. Land use, parks, water and buildings are shown in see-through colours. Export a colour map (PNG over the street or satellite map, or vector SVG) with legend, north arrow and scale bar; DXF (true coordinates, plot corner marks and IDs, coloured layers per category, road class and land use); KML (Google Earth / My Maps); CSV; and GeoJSON. Every export includes the plot corners. The site is line-hatched and labelled PROPOSED SITE in the DXF. Or add the surroundings and key plan to the layout sheet. |
| **B-07 Boreholes** | Place investigation points on the plan by clicking, by typing coordinates, or by pasting a list: boreholes 10 m and 20 m (BH), California bearing ratio (CBR) and permeability tests (PT), each with its legend symbol and an automatic ID. Drag to move, edit in the coordinate schedule. A drawing loaded as an underlay in the Measure tab shows here too. Export DXF (true coordinates, filled symbols, boxed labels, legend and schedule), CSV and PNG, or add the points, legend and schedule to the layout sheet. |
| **B-08 Footprint** | Bring in the proposed building footprint. **DXF is the exact route**: lines, polylines with arcs, circles, ellipses, splines and block inserts are read, loose lines are joined into closed outlines, and you pick the layers and drawing units; a drawing at a local origin can be centred on the site and then placed by dragging, by ΔE / ΔN, or by rotating. Corner coordinates can be pasted (also exact). A PDF or image is loaded as an underlay, calibrated in the Measure tab, and traced on the plan with corner snaps. DWG files must be saved as DXF first. Footprints show on the Boundary, Measure and Boreholes plans, the Surroundings map and the layout sheet, and go into every DXF export on a BUILDING layer. |

## Coordinate system

Pick the system your points are in from the toolbar: Bahrain (Ain el Abd / UTM 39N), WGS 84 UTM zones, Qatar, Dubai, Oman, Kuwait, Saudi systems, any UTM zone, or any EPSG code (looked up on epsg.io) or proj4 / WKT definition.

With a system set you get latitude / longitude for every point, the scale factor and convergence at the site, a combined scale factor worked out from the mean level, KML export for Google Earth, and lat / long columns in the CSV. Files in WGS 84 latitude / longitude (decimal or DMS) are converted on import, and **Convert points to it** re-projects a whole project into another system.

## CAD layout export

The layout DXF is drawn in model space at true coordinates. The boundary is a closed polyline at its real Easting and Northing, and the sheet frame, grid, schedules and title block are drawn around it at the chosen scale, on separate layers (LOGO, BOUNDARY, BOUNDARY_DIMS, POINTS, POINT_IDS, CORNER_COORDS, GRID, GRID_TEXT, AREA, TABLES, TITLE, NOTES, NORTH, SCALEBAR, SHEET). It drops straight onto other survey drawings, and plotting it at that scale gives the paper sheet.

Exports: layout DXF, quick DXF (layered), CSV, KML, SVG, PNG and print / PDF.

## Notes

- Everything runs in the browser. Files are read on your device and nothing is uploaded. The Surroundings tab sends only the site's centre and the search radius to the OpenStreetMap Overpass service.
- Surroundings data is © OpenStreetMap contributors (ODbL). Coverage varies by area and it is not surveyed, so use it for context only. Google's own map data can't be downloaded without a paid API key, so the app links to Google Maps instead.
- The PDF, spreadsheet, OCR and projection libraries load from a CDN the first time you use them, so those need an internet connection.
- Latitude / longitude uses the published datum shift for each system, good to a few metres. Grid distances, bearings and areas don't depend on it.
- Distances are plane (grid) distances from the coordinates you give. Check against your survey and project standards before setting out.

Prepared by Gouse Shaik, BIM Manager · MSCEB, Bahrain.
