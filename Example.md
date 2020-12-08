# The usd library 

The usd library graphs are built up with a few layers that each 
hold some core node for building usd assets and files. 

These single nodes when combined(parented or strung together)
 can build more complicated usd concepts. Please see the examples in this git repo
 for reference.

# Core layers

![Alt text](images/CoreUsdNodes.png?raw=true "CoreLayer")

All the core layers can be opened up in NXT by simply opening [pxr_usd_tools](graphs/pxr_usd_tools.nxt) or as individual layers.
At the moment there are 5 layer to draw from: [tools](graphs/pxr_usd_tools.nxt), [usd](graphs/pxr_usd.nxt), [geom](graphs/pxr_usd_geom.nxt), 
[model_api](graphs/pxr_usd_model_api.nxt) and [variants](graphs/pxr_usd_variants.nxt). 

I will be adding to these as I go along.

### pxr_usd

##### nodes

![Alt text](images/coreusd.png?raw=true "CoreNodes")

 - OpenOrFind: A more robust method of opening or creating usd files.
 - CreateNew: Creates a new empty layer with the given identifier.
 - StageOpen: Attempt to find a matching existing stage in a cache if UsdStageCacheContext objects exist on the stack. Failing that, create a new stage and recursively compose prims defined within and referenced by the layer at filePath, which must already exist.
 - RootLayerSave: Save out the Root layer to a stage.
 - GetPrimAtPath: Returns the prim at the given path.
 - GetPropertyNames: Return all of this prim's property names (attributes and relationships), including all builtin properties
 - GetAttribute: Return a UsdAttribute with the name given.
 - SetAttribute: Set a UsdAttribute with the name given.
 - SetDefaultPrim: Set the DefaultPrim of a stage.
 - GetDefaultPrim: Get the DefaultPrim of a stage.
 - AbsoluteRoot: Get the root path of a stage.

### pxr_usd_geom

##### nodes

![Alt text](images/geom.png?raw=true "GeomNodes")

 - Sphere: Construct a UsdGeom Sphere on UsdPrim. [details](https://graphics.pixar.com/usd/docs/api/class_usd_geom_sphere.html#details)
 - Cube: Construct a UsdGeom Cube on UsdPrim. [details](https://graphics.pixar.com/usd/docs/api/class_usd_geom_cube.html#details)
 - Mesh: Construct a UsdGeomMesh on UsdPrim. [details](https://graphics.pixar.com/usd/docs/api/class_usd_geom_mesh.html#details)
 - Cone: Construct a UsdGeom Cone on UsdPrim. [details](https://graphics.pixar.com/usd/docs/api/class_usd_geom_cone.html#details)
 - Points: Construct a UsdGeom Points on UsdPrim. [details](https://graphics.pixar.com/usd/docs/api/class_usd_geom_points.html#details)
 - NurbsPatch: Construct a UsdGeom NurbsPatch on UsdPrim. [details](https://graphics.pixar.com/usd/docs/api/class_usd_geom_nurbs_patch.html#details)
 - BasisCurves: Construct a UsdGeom BasisCurves on UsdPrim. [details](https://graphics.pixar.com/usd/docs/api/class_usd_geom_basis_curves.html#details)
 - Cylinder: Construct a UsdGeom Cylinder on UsdPrim. [details](https://graphics.pixar.com/usd/docs/api/class_usd_geom_cylinder.html#details)
 - NurbsCurves: Construct a UsdGeom NurbsCurves on UsdPrim. [details](https://graphics.pixar.com/usd/docs/api/class_usd_geom_nurbs_curves.html#details)
 - Capsule: Construct a UsdGeom Capsule on UsdPrim. [details](https://graphics.pixar.com/usd/docs/api/class_usd_geom_capsule.html#details)
 - DefinePrim: Construct a UsdGeom DefinePrim on UsdPrim. [details](https://graphics.pixar.com/usd/docs/api/class_usd_stage.html#a6151ae804f7145e451d9aafdde347730)
 - Xform: Construct a UsdGeom Xform on UsdPrim. [details](https://graphics.pixar.com/usd/docs/api/class_usd_geom_xform.html#details)

### pxr_usd_variants

##### nodes

![Alt text](images/variants.png?raw=true "VariantNodes")

 - AddVariantSet: Add a variant set to a prim of your choice.
 - AddVariant: Add a variant to a variant set.
 - SetVariantSelection: Set a variant selection of your choice.
 - GetVariantEditContext: Edit context to a selected variant.

### pxr_usd_model_api

##### nodes

![Alt text](images/modelapi.png?raw=true "ModelApiNodes")

 - ModelApi:
 - SetKind: Set a kind for a usd prim
 - SetAssetName: Give a prim a asset name
 - SetAssetVersion: Give a prim an asset version
 - SetAssetIdentifier: Sets the model's asset identifier to the given asset path
 - SetPayloadAssetDependencies: Returns the list of asset dependencies referenced inside the payload of the model.

See [ModelApiExample](examples/ModelApiExample.nxt) on how to use these nodes.
![Alt text](images/ModelApiexample.png?raw=true "ToolNodes")

### pxr_usd_tools

##### nodes

![Alt text](images/tools.png?raw=true "ToolNodes")

 - UsdView: Open up a usdview form inside nxt
 - UsdCat: Open up a terminal and cat usd file from within nxt
 - UsdDiff: Open up a terminal and diff usd file from within nxt
 - UsdConvert: Convert abc/usd file to usd file type of your choice.

### pxr_usd_layers

##### nodes

![Alt text](images/addlayergraph.png?raw=true "layeringNodes")

 - Reference stack: Open or create a reference for a given usd file.
 - Payload stack: Open or create a payload for a given usd file.
 - sublayer stack: Open or create a sublayer for a given usd file.

See [AddLayersExample](examples/AddLayersExample.nxt) on how to use these nodes.

# Example Layers
 - The following nxt graphs build example usd file based off of Pixar's [Tutorials](https://graphics.pixar.com/usd/docs/USD-Tutorials.html).
 - For and in depth look into how NXT works please see: [NXT_Tutorials](https://nxt-dev.github.io/tutorials/)
 - [HelloWorld.nxt](examples/HelloWorld.nxt)
    - Please see [HelloWorld](https://graphics.pixar.com/usd/docs/Hello-World---Creating-Your-First-USD-Stage.html) from pixar.

![Alt text](images/helloworld.png?raw=true "HelloWorld")
![Alt text](images/helloworld02.PNG?raw=true "HelloWorld02")
![Alt text](images/helloworld03.PNG?raw=true "HelloWorld03")
![Alt text](images/helloworld04.PNG?raw=true "HelloWorld04")
![Alt text](images/helloworld05.PNG?raw=true "HelloWorld05")
![Alt text](images/helloworld06.PNG?raw=true "HelloWorld06")
![Alt text](images/helloworld07.PNG?raw=true "HelloWorld07")
![Alt text](images/helloworld08.PNG?raw=true "HelloWorld08")

You can open up a usdview from inside NXT by running the usdview node.
Please insure you are running the correct path to your file.

![Alt text](images/usdviewpath.png?raw=true "usdviewPath")

Then simple execute from selected:

![Alt text](images/openupusdview.png?raw=true "Usdview")

 - [HelloWorldRedux.nxt](examples/HelloWorldRedux.nxt)
    - Please see [helloWorldRedux](https://graphics.pixar.com/usd/docs/Hello-World-Redux---Using-Generic-Prims.html) from pixar.

![Alt text](images/helloworldRedux.png?raw=true "HelloWorldRedux")

 - [AuthorVariants.nxt](examples/AuthorVariants.nxt)
    - Please see [AuthorVariants](https://graphics.pixar.com/usd/docs/Authoring-Variants.html) from pixar.

![Alt text](images/authoringvariants.png?raw=true "HelloWorldRedux")