# RBXMesh
A lightweight Python Library for parsing and exporting the Roblox Mesh Format supports Mesh V1 to V5

### Requirements
 - Python 3.10+ *( Older versions may work )*

### Dependencies
 - structs
 - dataclasses
 - sys

All dependencies used inside should already be installed with your python installation by default
### Helpful Resources
 - [Mesh Format Documentation](https://devforum.roblox.com/t/roblox-mesh-format/326114)

## Usage

### Reading Mesh
#### Command Line
> python3 RBXMesh.py ExampleMesh.mesh

#### Python
```python
from RBXMesh import FileMeshData, read_mesh_data

with open("ExampleMesh.mesh", "rb") as f: 
    meshBytes : bytearray = f.read()

meshData : FileMeshData = read_mesh_data( meshBytes )
```

### Exporting Mesh
#### Command Line
Supports exports in Mesh V2 and V3
> python3 RBXMesh.py ExampleMesh.mesh 2.0

> python3 RBXMesh.py ExampleMesh.mesh 3.0

#### Python
```python
from RBXMesh import FileMeshData, read_mesh_data, export_mesh_v2, export_mesh_v3

meshData : FileMeshData = read_mesh_data( meshBytes )

with open("ExportedMesh.mesh.v2", "wb") as f:
    f.write( export_mesh_v2(meshData) )
with open("ExportedMesh.mesh.v3", "wb") as f:
    f.write( export_mesh_v3(meshData) )
```

## Known Issues
 - Sometimes fails to parse Mesh V4.01