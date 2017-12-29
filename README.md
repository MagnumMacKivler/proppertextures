# GMOD Train Shared Textures Pack (GTSTP)
A shared material/textures pack for GMOD train addons.

## Wiki

Check the Wiki for material color vectors, material color codes, and more.

## Rules for contribution

* Your material needs GMOD and Hammer versions.
  
  GMOD compatible versions should include the full material files (such as normals, speculars, etc).
  
  *Hammer* compatible versions should not include these files, or `vertexlitgeneric` shader parameters. They need to be 
  `lightmappedgeneric` instead and never point to `models`. For example:
  
  ```
  "LightmappedGeneric"
  {
  
	  "$basetexture"		"proppertextures\paint\acrylic\acrylic_d"
	  "$bumpmap" 			"models\proppertextures\paint\acrylic\acrylic_n"
    
  }
  ```
  
  This is a perfect Hammer compatible material. Compare this to the original:
  
  ```
  "VertexLitGeneric"

{
	"$basetexture"			"models\proppertextures\paint\acrylic\acrylic_d"
	"$bumpmap" 			"models\proppertextures\paint\acrylic\acrylic_n"


	"$normalmapalphaenvmapmask"	"1"
	"$basemapalphaphongmask" 		"1"

	"$phong"			"1"
	"$phongalbedotint"		"0"
	"$phongtint"                  	"[1 1 1]"
	"$phongboost"                  	"0.15"
	"$phongexponent"             	 "7"
	"$phongfresnelranges"           "[1 5 8]"

	"$rimlight"               "1"
	"$rimlightexponent"       "10"
	"$rimlightboost"          "0.05"


	"$envmap"                       	"env_cubemap"
	"$envmaptint"                   	"[0.015 0.015 0.015]"
	"$envmapfresnel" 		"0.5"

	"$detail" 			"detail\plaster_detail_01"
	"$detailscale" 		"30.283"
	"$detailblendfactor" 	"0.15"
	"$detailblendmode" 	"0"

  }
  ```
  Certain Hammer materials will need different `basetexture` files. Colored cabmetal, for example, would need a precolored VTF (not colored in the VMT) because color in the VMT does not show up in Hammer.

* Follow the naming and folder location conventions.

  This means you need to look at our files, see how we do things, and follow that. For example:
  
  * Don't "one-off" everything. This means if multiple builders used a type of vent, but you made the vent for one thing, don't name the vent material `alco_vent`. Instead name it `vent_striped` (or something to that effect), depending on what you're making.
  
  * Don't put VMTs in another folder. Leave them in the main directory. The VTFs should go into a place we made already, but you may have to make a new folder if it's _very unique_.
  
  * Try to avoid putting a number at the end of a file. Instead, the name should be somewhat descriptive. Exceptions may be our wood materials, as they're literally all just different wood textures.
  
* Put in effort, and make it quality.

  This should go without saying, but it needs to be stated. We do have a few things we would like (if possible) in your material. These include:
  
  * Normal maps (if needed). Normal maps are required for many shaders, such as phong, so you may need them for shiny materials. Only some special materials do not benefit from normal maps.
  
  * Specular maps (if needed). Speculars should be used to improve the quality of materials (like metal) that should be shiny. These are used for enviorment cube maps, not for diffuse phong reflections. They shouldn't be overly strong in the VMT.
  
  * "3D" materials (like fans) should probably have transparency (alpha included in the diffuse). 3D models should have black bottoms to give the fans (or anything!) some 3D effect.
  
  Another thing we suggest is to really spend some time to see how your shader parameters look. Things shouldn't be overly reflective, shiny, or pixeliated (zoomed in).
  
* Include screenshots with your pull request.

  We need to review your pull request. Don't make it hard on us to do so, not all of us are going to download these changes to check them.

## Updating Local Files through SVN

Tortoise SVN can be used to easily update your local files.
For Hammer Textures:
* Make a new folder called `proppertextures` inside `Propperconfiguration\materials`.
* Right Click it and click SVN Checkout.
* Use this link for the repository: `https://github.com/MagnumMacKivler/proppertextures/trunk/hammer/materials/proppertextures`

For GMOD Textures:
* Make a new folder called `proppertextures` inside `garrysmod\materials\models`.
* Right Click it and click SVN Checkout.
* Use this link for the repository: `https://github.com/MagnumMacKivler/proppertextures/trunk/gmod/materials/models/proppertextures`

After this is done, either directory can be updated by Right-Clicking the `proppertextures` folder and clicking SVN Update.
