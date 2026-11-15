# Boundary Distance Solver

Read site coordinates from a PDF, Excel/CSV, image or manual entry. See the boundary drawn with every distance, bearing and area, and measure anything on screen with CAD-style snaps.

**Live:** https://gs-786.github.io/Boundary-Distance-Solver/

## Tabs

| Tab | What it does |
| --- | --- |
| **B-01 Coordinates** | Import a PDF schedule (text layer, or OCR if scanned), Excel/CSV, a photo or screenshot (OCR), or pasted text. Review the columns it found, then replace or append. Edit points by hand. |
| **B-02 Boundary** | Zoomable plan with edge distances, bearings, point IDs, coordinates and area. Hover a corner or edge for details. |
| **B-03 Distances** | Every edge with ΔE, ΔN, distance, bearing, ground distance (scale factor) and slope/grade when levels exist. Point-to-point calculator and distance matrix. |
| **B-04 Measure** | Distance, path, area, angle and square offset to the boundary. Snaps to corners, midpoints, edges, perpendiculars and earlier measurements; Shift for ortho. Load a PDF page or image as an underlay and calibrate it by drawing scale, a known distance, or two known coordinates. |

Exports: DXF (layered), CSV, PNG and print.

## Notes

- Everything runs in the browser. Files are read on your device and nothing is uploaded.
- The PDF, spreadsheet and OCR readers load from a CDN the first time you use them, so those need an internet connection.
- Distances are plane (grid) distances from the coordinates you give. Check against your survey and project standards before setting out.

Prepared by Gouse Shaik, BIM Manager · MSCEB, Bahrain.
