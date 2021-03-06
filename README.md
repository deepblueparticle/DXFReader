## DXFReader
This code implements a simple DXF file parser that can read many 2D DXF files containing ARC, LINE, POLYLINE, LWPOLYLINE and SPLINE outlines such as those used for embroidery patterns and input to machines like Silhouette paper cutters.  It's designed to convert POLYLINE, and other DXF elements into an array of Path2D.Double objects from Java's geom package.  The parser looks for a $INSUNITS attribute in the DXF file's header to try and determine the measurement units used but, if none is found, it assumes that DXF file's units are millimeters.  Internally, the code converts everything into inches and you can also pass the parser maximum and minimum size values (in inches) and it will scale the converted shape up, or down, as needed, to fit within these limits. The code also contains a simple viewer app you can run to try it out on a DXF file.  From the command line type:

    java -jar DXFReader.jar file.dxf
    
You can download an already built DXFReader.jar file [by following this link.](https://github.com/wholder/DXFReader/tree/master/out/artifacts/DXFReader_jar)
        
I've tested this code with a variety of simple, 2D DXF files and it's able to read most of them.  However, the DXF file specification is very complex and I have only implemented a subset of it, so I cannot guarantee that this code will read all 2D DXF files.
### Requirements
DXFReader requires Java 8 JRE or [Java 8 JDK](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html), or later to be installed.
### License
I'm publishing this source code under the MIT License (See: https://opensource.org/licenses/MIT)