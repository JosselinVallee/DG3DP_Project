###################################################################
############################# README #############################
###################################################################
################ 3D GEOMETRY PROCESSING PROJECT###################
###################################################################
#################################################################


In the folder data we included the 3 meshes geralt_high_res, gears_high_res and projected_gears and the file colors.txt.

In the folder curvature we provide our code:
 
1) In file viewer.cpp we provide the implementations of the functions needed to generate the final mesh.

2)In the file viewer.h we provide the implementations of the loading of the meshes and grafical tools.

3)The file curvature.cpp is the main to execute.

 
How to run the code:

1)execute the curvature project. The three meshes are loaded simultaneously. Using the button visibilty you can choose which meshes to display. By default Gears and Geralt will be visible. The 3rd is Gear Surface which is the output of an intermediate step in our pipeline since we go back and forth between qtcreator and mesh mixer.

2)We have kept some useful methods from previous labs, like display wireframe, normals, valence, curvature and the mesh enhancement.
  It possible to open a new mesh or export a mesh with the corresponding buttons.

3) Pressing the button Zones, you have a lot of methods to apply to the  meshes:

	A) Calculate: it calls the function findIntersectionFast that finds the faces of geralt that intersect a ray from a vertex of the gear to the center.
		      At the end it displays the colored faces on Geralt.

	B)Fill Gears: it fills the gear. After executed Calculate the resulting projected gears has a lot of little undesired holes. This function fixes this issue.

	C)Pick Holes: using this button it is possible to manually select the holes. Camera rotation and and panning is disabled in this mode however.

	D)Cut Holes: it deletes the Hole zones on Geralt creating holes.

	E)Extrude: it extrudes the projected_gears mesh by 2 mm outwards. After that the mesh must be saved using the "Save a mesh" button

	F)Load from file:it loads the colors from the file colors.txt. It displays the different zones on the gerlat's face.

	G) Save to file: it save the colors of geralt in the file colors.txt and it generates the file gearCloud.obj that contains the gears projected on Geralt. 


Pipeline to generate the two meshes needed for the final mesh (see report for details)

1)Geralt_holes : run calculate, fill Gears, pick Holes(picking the correct holes), Cut Holes and Save to File. Alternatively, it is possible to load the file precomputed_colors 
		(move the colors.txt file from the folder precomputed_colors_file to data) and then Cut Holes and Save to file. This is recommended as the complete pipeline takes around 5 hours to run)

2) Projected_Gears_Thick : 
When we clicked ‘Save to file’ in step G we also generate gearCloud.obj.
After smoothing this in meshmixer and exporting we obtain projected_gears.obj which is the  final gear mesh that we want to extrude.

Thus we load the mesh into our project and click: Extrude and Save Mesh -> projected_gears to obtain the final Projected_Gears_Thick.