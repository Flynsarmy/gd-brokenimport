# Godot Broken GLTF Import Example

Demonstrates a bug with the GLTF importer in Godot 3.5.1

## Requirements

* Godot 3.5 or 3.5.1 RC 1
* Blender 3.3.0

## Steps to Replicate

* In blender 3.3 create an empty scene.
* Add a default cube.
* Add a second material and assign some faces to the second material. No complicated changes necessary, just change its colour or something.
* Export as GLTF 2.0 with default settings into your Godot project.
* Godot will import correctly with the two materials being created and the GLB having a cross icon:
![image](https://user-images.githubusercontent.com/334808/190558097-44598bb5-e299-4175-ba95-10a7d3bdd301.png)
* Make any change in blender then re-export and overwrite your GLB file
* Godot will re-import but error. The GLB icon is no longer a cross, but output has the following error:
![image](https://user-images.githubusercontent.com/334808/190558233-0a57dbca-1cfb-45cd-b5a9-e2bf4963cb6d.png)

> editor/editor_file_system.cpp:1724 - BUG: File queued for import, but can't be imported!
 editor/editor_file_system.cpp:1725 - Method failed.
 editor/editor_file_system.cpp:1724 - BUG: File queued for import, but can't be imported!
 editor/editor_file_system.cpp:1725 - Method failed.