The project is expandable library geospatial vector functions based on SQL, PostgreSQL, PostGIS software environment.

Programming language - SQL.

Instructions for installing, verifying the creation, operation and deletion of the function

1. The following software must be installed on the PC, laptop or JVM to work with the function library: PostgreSQL, PostGIS and pgAdmin.

2. Installing, checking the creation of the function, operation and deletion of the function

2.1 To install the required function it is necessary to launch the pgAdmin application, enter the password, connect to the spatial database and select the working schema, then on the control panel it is necessary to find and select the “Tools” button, then in the drop-down field with a list select the field named “Query Tool” and activate the field by clicking the left mouse button. In the workspace named “Query Editor” it is necessary to copy and paste the required function and run it for execution (add it to the library of database/space database functions) using the button located on the PC keyboard named “F5” or the program button in the form of an equilateral triangle with a vertical base named “Execute/Refresh (F5)” located on the pgAdmin toolbar. 

2.2 To check the creation of a new function, it is necessary to enter the main library of database/space database functions (Functions(count)) located in alphabetical order in the main tree of the active database/space database and make sure that the function has been created.

2.3 To check the work of the created function in the workspace named “Query Editor” it is necessary to run a query with the following structure “SELECT new function name with setting the necessary values of function parameters” and get the result of its execution.

2.4 To delete a function in the workspace with the name “Query Editor” pgAdmin it is necessary to run a query in the form “Drop function, function name, function parameters”.
   
3 The library of all functions is presented in the download folder with the name “PostGeoSQL-main” in the form of files with the name of the function. The file is opened with a text editor such as Notepad++, WordPad or similar.

4. An example of creating, checking operation and deleting a function is given below.

4.1 Create a function

<CREATE OR REPLACE FUNCTION generate_identical_numbers_notnull_interval_ascending_order(
    k integer,
    i integer)
RETURNS TABLE (x integer) AS 
$BODY$
      SELECT n
      FROM generate_series(1, k) n 
           , generate_series(1, i) x  
      ORDER BY n, ((x%2 * 2) - 1) * n;
$BODY$
LANGUAGE SQL>

4.2 Run the function for execution

<SELECT generate_identical_numbers_notnull_interval_ascending_order(5,3) gini>

4.3 Remove the function from the main function library

DROP FUNCTION IF EXISTS generate_identical_numbers_notnull_interval_ascending_order(
    k integer,
    i integer)

A brief description of how geo-functions work is generally published on the Q&A website at the following link - https://gis.stackexchange.com. 
The authors and developers of the functions body used in the project is:

© Martin Davis https://github.com/dr-jts;

© Erwin Brandstetter https://dba.stackexchange.com/users/3684/erwin-brandstetter;

© mustaccio https://dba.stackexchange.com/users/23721/mustaccio.

Links to published SQL/GeoSQL functions on the Q&A website:
1) ST_VoronoiDiagramsFromPolygons - https://gis.stackexchange.com/a/318112/120129;
2) ST_VoronoiDiagramsFromLines - https://gis.stackexchange.com/a/348154/120129;
3) ST_PerpendicularTransectsFromLine - https://gis.stackexchange.com/a/473663/120129;
4) ST_PerpendicularTransectsFromRiverLine_v1, ST_PerpendicularTransectsFromRiverLine_v2 - https://gis.stackexchange.com/a/473783/120129;
5) ST_RaysInGridPolygons - https://gis.stackexchange.com/a/443283/120129;
6) ST_RegularPointsGridOfCornerPoints - https://gis.stackexchange.com/a/438068/120129;
7) ST_Linestopolygons - https://gis.stackexchange.com/a/470364/120129;
8) ST_PointsInStarPolygonFromDelaunayTriangles - https://gis.stackexchange.com/a/368121/120129;
9) ST_LongestAxisPolygonsFromVoronoiDiagrams, ST_LongestAxisPolygonsFromVoronoiDiagrams_gs, ST_CentraLAxisLongestLineFromPolygons_VD - https://gis.stackexchange.com/a/347625/120129;
10) ST_AvgLengthLineIRRegularPolygon - https://gis.stackexchange.com/a/418990/120129;
11) ST_MaxDistanceWestEastIRRegularPolygon - https://gis.stackexchange.com/a/418891/120129;
12) ST_SnapPolygonToLine - https://gis.stackexchange.com/a/408355/120129;
13) ST_MergingTwoIsolinesOneAverage - https://gis.stackexchange.com/a/375525/120129;
14) ST_BambooBuffer - https://gis.stackexchange.com/a/309043/120129;
15) ST_CentroidOnSurface_v1,  ST_CentroidOnSurface_v2 - https://gis.stackexchange.com/a/372944/120129;
16) ST_MaximumAreaInscribedRectangleInPolygon - https://gis.stackexchange.com/a/368504/120129; https://gis.stackexchange.com/a/475627/120129;
17) ST_CentraLAxisLongestLineFromVoronoiDiagrams - https://gis.stackexchange.com/a/411894/120129;
18) ST_SmoothingPolygonsNotchesInternalVertices - https://gis.stackexchange.com/a/467857/120129;
19) ST_SamplingLargePolygonsByDoubleBufferization, ST_SamplingSmallPolygonsByDoubleBufferization - https://gis.stackexchange.com/a/316212/120129;
20) ST_CarvesPolygons - https://gis.stackexchange.com/a/333562/120129; https://gis.stackexchange.com/a/302470/120129;
21) ST_SmoothedToothedPolygonExternal, ST_SmoothedToothedPolygonInternal - https://gis.stackexchange.com/a/429894/120129;
22) ST_ExtractionExternalGridCells, ST_ExtractionExternalGridCellsByDoubleBufferization  - https://gis.stackexchange.com/a/350076/120129;
23) ST_RoadAxis - https://gis.stackexchange.com/a/340590/120129;
24) generate_numbers_interval_as_descending_order, generate_numbers_interval_des_ascending_order, generate_numbers_notnull_dupl_border_interval_ascending_order, generate_identical_numbers_notnull_interval_ascending_order - https://dba.stackexchange.com/a/337260/222586; https://dba.stackexchange.com/a/337294/222586;
25) ST_BufferClusteringRequiredDistance - https://gis.stackexchange.com/a/312261/120129;
