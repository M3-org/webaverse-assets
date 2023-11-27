# **Manifest Setup for Character Studio**
This guide will help you create your own manifest for character studio. Manifests for character studio are written in json style and its used to tell character studio how its going to work.

# Main Manifest
This manifest serves the character studio to know where its going to fetch each of the character's manifests, there can only be one of this per character studio project, but can load as many character manifest as you wish.

# Character manifest
This manifest includes important information for the character studio to work, setting it up, helps the character studio know how to arrange, load and cull trait models correctly.

The manifest is divided in 3 sections:



## Main Section
Includes generic and important information such as root assets location, and trait default values.

### assetsLocation
*(required string)*

Root location where all assets will be taken from:

Example:
```json
"assetsLocation":"./character-assets/"
```
```json
"assetsLocation":"https://memelotsqui.github.io/character-assets"
```

### traitsDirectory
*(optional string)*

Alternative subfolder location where your traits will be loaded from:

Example:

```json
"traitsDirectory":"/traits/"
```

Character studio will search on assetLocation + traitsDirectory: 

```./character-assets/traits/```


### thumbnailsDirectory
*(optional string)*

Alternative subfolder location where thumbnails for traits will be loaded from:

Example:

```json
"traitsDirectory":"/traitsThumbnails/"
```

Character studio will search on assetLocation + thumbnailsDirectory: 

```./character-assets/traitThumbnails/```


### traitIconsDirectorySvg
*(optional string)*

Alternative subfolder location where thumbnails for traits will be loaded from:

Example:

```json
"traitsDirectory":"/traitsThumbnails/"
```

Character studio will search on assetLocation + thumbnailsDirectory: 

```./character-assets/traitThumbnails/```

### animationPath
*(optional string array)*

Animations that will played on the character for previewing, in case of using vrm traits, you may use Mecanim animations.

Example:

```json
"animationPath":["/animations/idle.fbx", "/animations/t-pose.fbx"]
```
Character studio will search on root directory + each animation path:

```./character-assets/animations/idle.fbx```

### exportScale
*(optional number)*

Default export scale value for character when downloading and previewing, default is 1

Example:
```json
"exportScale":0.7
```

### requiredTraits
*(optional string array)*

Trait group names that must have at least one option selected. Trait group names are defined inside trait collections.

Example:
```json
"requiredTraits":["BODY", "CLOTHING"]
```

### randomTraits
*(optional string array)*

Trait group names that will be ransomized when clicking ransomize button. Trait group names are defined inside trait collections.

Example:
```json
"randomTraits":["CLOTHING", "HAIR"]
```

### defaultCullingLayer
*(optional number)*

Default culling layer for every trait model in the collection, can be overriden by its trait group culling layer, or its directly within the trait. Default is -1. Use integers only.

Culling layers go from -1 to any number. Lowest layer number trait (starting from 0) will get culled by higher layer number trait. Layers with number -1 will be ignored in this process.

Example:
```json
"defaultCullingLayer":0
```

### colliderTraits
*(optional string array)*

---

Example:
```json
"randomTraits":["BODY"]
```

## Trait Group Section 
Includes trait collection and group specific information such as culling values.

## Trait Section
Includes trait specific information such as location and overridable culling values. 

## Texture Collection Section
Used to define a collections of textures that can be assigned to specific traits.

## Color Collection Section:
Used to define a collections of colors that can be assigned to specific traits.

