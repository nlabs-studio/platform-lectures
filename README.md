# File Data Format Web Application IO

The clear text file format for imports / exports into live web application is described here. Its a relatively simple format at this moment given that it need only accommodate some basic volumetric inputs.

# Data File String Example

Untitled[]cube:RmlsdGVy:150#cylinder:SW50YWtl:100:1200#cylinder:UGFzc3RocnU=:100:2000#rectangular_tank:UmVzZXJ2b2ly:2000:300:300@1=1=1=1

The above example describes a water cooling solution which consists of a {Cpu_Filter, Intake, Passthru, Reservoir}. The shapes respectively in this instance are of the forms {Cube, Cylinder, Cylinder, Rectangular_Tank} respectively.

The string begins with the tab name, for non web application purposes, this may be omitted. Next is the delimitor []. Followed is the internal geometric shape, the "cube" followed by the next delimitor type ':'. The delimitor ':' is used to separate geometric properties. In the case of this cube, only two properties need be provided, these include its label and its edge length defined in millimeters.

The initial form is always SHAPE_TYPE:LABEL. The LABEL is a base64 encoding. The properties which follow are numerics exclusively relative to the shape type. For an example, a cube will have less properties than a cylinder and indeed the cylinder lesser properties than a stadium frustum.

The '#' delimitor is used to split shape types 

# Metric Used

The numeric metric used in the file data format is always the millimeter. The application is responsible for converting between distinct types of meters.

# List of Delimitors

[] - splits name of tab and volume list data
:  - splits properties of geometric object
\#  - splits objects of volume recipe list
@  - splits scaling constants from objects
~ - (reserved) splits multiple tabs iff export is a workspace export

# List of Geometric Shapes

Current verifiable list may be found here: https://github.com/volume-cc/geometric-list/
