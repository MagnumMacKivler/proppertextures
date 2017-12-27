# GMOD Train Shared Textures Pack (GTSTP)
A shared texture pack for GMOD train addons.

## Rules for contribution

* Follow the naming and folder location conventions

  This means you need to look at our files, see how we do things, and follow that. For example:
  
  * Don't "one-off" everything. This means if multiple builders used a type of vent, but you made the vent for one thing, don't name the vent texture `alco_vent` or something like that. Instead name it `vent_striped` (or something to that effect), depending on what you're making.
  
  * Don't put VMTs in another folder. Leave them in the main directory. The VTFs should go into a place we made already, but you may have to make a new folder if it's _very unique_.
  
  * Try to avoid putting a number at the end of a file. Instead, the name should be somewhat descriptive. Exceptions may be our wood textures, as they're literally all just different wood textures.
  
* Put in effort, and make it quality.

  This should go without saying, but it needs to be stated. We do have a few things we would like (if possible) in your texture. These include:
  
  * Normal maps (if needed). Normal maps are required for many shaders, such as phong, so you may need them for shiny textures. Only some special textures do not benefit from normal maps.
  
  * Specular maps (if needed). Speculars should be used to improve the quality of textures (like metal) that should be shiny. These are used for enviorment cube maps, not for diffuse phong reflections. They shouldn't be overly strong in the VMT.
  
  * "3D" textures (like fans) should probably have transparency (alpha included in the diffuse). 3D models should have black bottoms to give the fans (or anything!) some 3D effect.
  
  Another thing we suggest is to really spend some time to see how your shader parameters look. Things shouldn't be overly reflective, shiny, or pixeliated (zoomed in).
  
* Include screenshots with your pull request.

  We need to review your pull request. Don't make it hard on us to do so, not all of us are going to download these changes to check them.
