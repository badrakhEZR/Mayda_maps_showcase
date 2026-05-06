# Mayda Maps Architecture

Mayda Maps is a Ulaanbaatar-focused AI map and navigation product.

## System Overview

```text
Frontend Map UI
    |
    | HTTP API
    v
FastAPI Backend
    |
    | SQL / Spatial Queries
    v
PostgreSQL + PostGIS
    |
    | Data Quality Pipelines
    v
Buildings / Entrances / POIs / Bus Routes / Stops / Address Registry
Core Components
Frontend

The frontend is a map-based interface built with Leaflet.

Main responsibilities:

Render map layers
Show search results
Show place and building detail cards
Draw walking and bus route geometry
Display bus route cards
Handle route tracking UI states
Backend

The backend is powered by FastAPI.

Main responsibilities:

Search API
Building layer API
Entrance layer API
Bus planner API
Road geometry API
Address registry search
Data confidence and ranking logic
Database

PostgreSQL/PostGIS stores location-aware data.

Main data groups:

Buildings
Entrances
POIs
Bus routes
Bus stops
Address registry
Walking and road geometry
Data Quality Pipeline

Mayda Maps does not treat every imported data point as trusted.

The system uses:

Candidate records
Confidence scores
Manual review flags
Active / weak / rejected status
Geometry validation
Route quality checks
Mobile Direction

The frontend can later be wrapped into a mobile app using a web-to-native shell such as Capacitor after the route rendering and API boundaries are stable.


6. Доош scroll хийгээд **Commit changes** дар.

7. Commit message:
   ```text
   Add architecture documentation
