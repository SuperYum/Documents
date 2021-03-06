# Components Features Overview

### MapKit - WebAPI
Compatible with .NET and .NET Core

- All Features of MapKit - Core
- MapModel
- XYZ imagery action result
- Bound imagery action result
- Cross-platform support with Mono

### Core Features
Compatible with .NET and .NET Core

- Geometries
    - Geometry Types  
        - Point
        - MultiPoint
        - Line
        - MultiLine
        - Polygon
        - MultiPolygon
        - GeometryCollection
    - WKT / WKB / Vertex Conversion
- Spatial Functions
    - Relations
        - Check contains
        - Check crosses
        - Check disjoints
        - Check within
        - Check intersects
        - Check overlaps
        - Check topologically equals
        - Check touches
    - Process
        - Find closest point
        - Buffer geometry
        - Get convexhull
        - Get difference between two geometries
        - Measure distance
        - Get intersection
        - Get shortest line to a geometry
        - Get centroid/center of a geometry
        - Get bound of a geometry
        - Scale a geometry up / down
        - Rotate a geometry with an origin
        - Union two area geometries
        - Find a segmentation on a line
        - Fine a point on a line
- Symbologies
    - Fill Style
    - Line Style
    - Point Styles
    - Label Style
    - Thematic Style
    - Field value Style
    - Heat Style
    - Css Style
- Renderers
    - Gdi+ 
- DataFormats
    - Vectors
        - Dynamic Features
        - Shapefile
        - Grid (Memory/File)
        - Sqlite (~~Not compatible with .NET Core~~)
        - PostgreSQL (~~Not compatible with .NET Core~~)
    - Rasters
        - OpenStreetMap
        - GoogleMaps
        - BingMaps
        - StamenMaps
        - Imagery (eg. *.png, *.jpg etc.)
        - Wms
        - Tiff
    - Layer Group
- Projection (*vector only*)
    - Spherical Mercator
    - UTM
    - State Plane
    - National Grids
    - WGS84
    - NAD83
    - And more...


