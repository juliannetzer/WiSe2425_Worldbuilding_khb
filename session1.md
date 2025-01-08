# Session 1

# <a name="project">Creating a new project

Go to the Unity Hub and click on "New project"
![](images/newproject1.jpg)

Then select "3D URP", choose a name for your project and click on "Create project"
![](images/newproject2.jpg)


# <a name="editor">Working with the Unity Editor

## General Unity Glossary

### Unity Hub
The Installer for different Unity versions and the place to open all of your Unity projects 

### Unity Editor 
The Unity programm itself, where you design your game 

### Build 
when you are finished with your game, you can export your game as a build, which means that the game can be played on different platforms without the Unity Editor. 

### Project 
The project consists of all the elements that make up your game, it is a folder on your harddrive. 

### Scenes 
Scenes are like levels in your game, each level usually is made out of one scene. In the scene you basically save how your Assets are linked to each other (how they are placed in the scene, how they interact etc.). You can have as many scenes as you like in your game and not every scene has to be in the final game. 

### Assets 
Assets are all Elements in Unity that are saved as a file on your computer. For example 3D-Objects, Materials, Scripts etc. 

### GameObjects
GameObjects are the virtual objects in your Unity Scene, they are not saved as a file in your assets folder, but they only exist within the scene. (If you want to create an Assets out of a GameObject you can create a PreFab.) 

### Component 
Components are the functional pieces of every GameObject. Each GameObject is made out of different components, e.g. the "Mesh Renderer" tells Unity that this is an object that should be rendered (should be visible) in the scene. 

## Unity Editor User Interface

![](images/UnityUI.jpg)

### 1. Project windows: 
- a file explorer, where you can find all of your assets 
- Unity projects are always a folder consisting of different file types (in contrast to e.g. a Blender file). That means if you press save, you only save the current scene, the rest of your project in saved in the folder. 

> Data backups: always duplicate the entire folder, ideally always copy the entire folder before making major changes. Alternatively: Use a version control system like git. 

### 2. Hierarchy
- In the Hierarchy you can find all the GameObjects that are in your currently opened scene
- Here you can also see how the objects are arranged hierarchically (Parent-Child)

### 3. Inspector
- shows you all the Components that are part of the current GameObject when you select a GameObject
- also shows you the properties of all the Assets when you select an Assets
- allows you to change the properties of the different Components & Assets

### 4. Scene View 

![](images/SceneView.jpg)

- Displays the current 3D scene
- Move with: 
	- Rotate: option + mouse click
	- Move: option + command + mouse click
	- Zoom: Two finger scroll 
	- double-click on object: focus on object 
- Use the Scene Gizmo (a) to switch to a single axis view 
- You can switch between 2D & 3D view (b) (helpful for UI work)
- You can change the perspective mode (c)
- Toggle visibily of gizmos (d)
- Tools to move/rotate/scale objects (e)


### 5. Game View 
- shows the game as it will look later when the player will play it
- if you press "Play" at the top of the screen, a preview of how the game will look later is displayed here 
- here you can preview the game in different screen sizes etc. 
- most of the animations/scripts etc. only run when you have pressed play

### 6. Toolbar 
- Control the Game Mode of the current scene

### 7. Menubar
- can be used to create Assets, GameObjects, change the window-arrangement, save the current scene etc. 

You can find a Cheat Sheet with the Basic Unity UI Elements here: 
https://github.com/juliannetzer/arfoundation-demos_khb_sose22/blob/master/Handouts/220501_UnityCheatsheet.pdf

## Further tutorials for getting started in Unity: 
- [Everest Pipkin: Quickstart Unity 3d ](https://docs.google.com/document/d/1xwGpjgIRhZAqprW-jECGN1WNh_o2jfO_84hjLQ59TIQ/edit)
- [Brackeys: How to make a Video Game - Getting Started](https://www.youtube.com/watch?v=j48LtUkZRjU&list=PLPV2KyIb3jR5QFsefuO2RlAgWEz6EvVi6)
- [Ray Wenderlich: Unity Getting started](https://www.kodeco.com/7514-introduction-to-unity-getting-started-part-1-2)
- [The Ultimate Beginner Guide to Unity](https://www.freecodecamp.org/news/the-ultimate-beginners-guide-to-game-development-in-unity-f9bfe972c2b5/)


# <a name="structure"></a> How to structure your unity projects
Since Unity projects quickly get very messy it is important to structure your assets & scenes, you can find some useful information here: 

[Best practices of organizing your unity project](https://unity.com/how-to/organizing-your-project)

# <a name="materials"></a> Materials/ Shaders/ Textures 

Every 3D-Assets in Unity needs a material that is attached to it, and every material needs a shader. The material is the place where the information like colors and textures are stored. The shader then tells unity how to render these information. (you can compare it to using a pencil: the material stores the color, the shader stores whether it is a wax crayon or a colored pencil). 

Most materials have a certain set of textures (images) applied. The most important ones in Unity are: 
- Albedo/ Base Map
- Specular Map
- Normal Map
- Height Map 
- Occlusion Map

## Create a new material: 

Click on Assets -> Create -> Material

Now you can add some textures and change the colors. 
To apply the material to an object, just drag and drop it onto the object. 

### Best Places to get free Textures: 
- [Polyhaven](https://polyhaven.com/textures)
- [Unity Asset Store](https://assetstore.unity.com/?category=2d%2Ftextures-materials&free=true&orderBy=1)
- [AmbientCG](https://ambientcg.com/)
- [Ponzu (AI generated Textures)](https://www.ponzu.gg)

### Settings for Polyhaven: 

- Resolution: 2K (or on better machine, or complex textures 4K)
- ZIP 
- .JPGs (or for better quality .PNG)

Conversion Table for using Polyhaven Materials: 
| Unity            | Polyhaven   |
| ---------------- | ----------- |
| Albedo/ Base Map | Diffuse     |
| Specular Map     | Spec        |
| Normal Map       | Normal (GL) |
| Height Map       | Displacement|
| Occlusion Map    | AO          |

# <a name="3dassets"></a>Working with imported 3D Assets
![](images/assets.jpeg)

Most of the times the 3D-Assets are not generated outside of Unity and then imported into the project.

To import Assets into your project, just drag and drop them into the "project"/Assets-window

Supported file formats: 
- .fbx (usually works best) 
- .obj 
- .dae
- .3ds
- .dxf

Note: you can also use other file formats (link .blend etc. if the corresponding software is installed but i wouldn't recommend it) 

[Unity Documentation on file formats](https://docs.unity3d.com/2020.1/Documentation/Manual/3D-formats.html)


## Best places to get free 3D-Assets 

- [Unity Asset Store](https://assetstore.unity.com/?category=3d%2Fenvironments&free=true&orderBy=1): Large library of assets, specifically for unity, sometimes with animations 
- [Sketchfab](https://sketchfab.com): Large library for free Assets, also from museums etc., mixed quality & licenses 
- [Mixamo](https://www.mixamo.com/): Large library of (mostly) humanoid Avatars & Animations
- [Polyhaven](https://polyhaven.com/models): Not that many models, but all can be used for any purpose (commercial and personal)
- [Everything library](https://davidoreilly.itch.io/): library of objects from the (very good) game "Everything", see hint below, a lot of models, all in the same style (low poly), can be used in all projects, but an attribution is necessary[license](https://creativecommons.org/licenses/by/4.0/)
- [NASA 3D Models](https://nasa3d.arc.nasa.gov/models): library of space related objects, different quality, but some are quiet nice
- [Three D Scans](https://threedscans.com/): library of 3d scanned statues & some animals, very detailed 
- [ArtStation](https://www.artstation.com/marketplace/game-dev/assets?section=free): Plattform, mixed quality, different
- [Quaternius](https://quaternius.com/): nice low poly packs, most of them free to use
- [OpenGameArt](https://opengameart.org/art-search-advanced?keys=&field_art_type_tid%5B%5D=10&sort_by=count&sort_order=DESC): a lot, mixed quality
- [Dimensiva](https://dimensiva.com/free-3d-models/): mostly furniture

> Trees are rather difficult to render in Unity, so either use Low-Poly Versions, or you can also find some in the Assets Store (e.g. [Realistic Pines](https://assetstore.unity.com/packages/3d/vegetation/trees/realistic-pine-tree-pack-232166), [Polygon Trees](https://assetstore.unity.com/packages/3d/vegetation/trees/polygon-trees-224068))


## Online Sculpting Tools
![](images/sculptgl.jpeg)
- [SculptGL](https://stephaneginier.com/sculptgl/)
![](images/monstermesh.jpeg)
- [Monster Mash](https://monstermash.zone/)

## AI Tools
![](images/lumalabsgenie.jpeg)
- [Lumalabs Genie](https://lumalabs.ai/genie?view=create)
![](images/hyper3d.jpeg)
- [Hyper3D - Rodin](https://hyper3d.ai/)

## Troubleshooting

### Material is displayed pink: 
Probably a problem with the renderpipeline, find the material in the project window, select it and then click on "Edit -> Rendering -> Materials -> Convert Selected Built-in Materials to URP". If this does not work, either create a new material and assign it, or if you can get the asset in a different fileformat try that. 

### Imported object does not have a color/texture 
- See whether the asset comes with a "material" or "texture" folder, if yes, try: 
	- select the 3D-model in the project window, and go to the "Materials"-Tab in the Inspector window, select Location -> Use External Materials (Legacy) and click "Apply"
	- If this does not work: switch to Location -> Use Embedded Materials again and click on "Extract Materials" and then on "Apply". This extract the Materials from the model and you can manually assign the textures/colors etc. 
- If it does not come with an extra folder: 
	- select the asset in the Project window and click on "Extract Textures" and/or "Extract Materials" in the Inspector (in the "Materials" Tab)
	-  If there are still no materials/textures you have to manually create them/ or find a new asset

# <a name="perfomance"></a>Performance?

Especially when choosing the 3D assets and lights, you should have in mind where your scene will be played in the end, e.g. as desktop VR, i.e. on a powerful computer, or in mobile VR (e.g. an Oculus Quest). As all devices only have a limited performance capacity. For the quest there is a website which gives you an good overview: 
https://developer.oculus.com/documentation/unity/unity-perf/

We are gonna stick with the triangle xount for now, this is the information on the quest website: 
| Platform         | Triangle Count   |
| ---------------- | ---------------- |
| Quest 1          | 350k-500k        |
| Quest 2          | 750k-1.0m        |


You can now compare this to the triangle count in your Unity scene:
Go to Game View and toggle "Stats" you can now see the Triangle Count 
![](images/triangle.jpg)

If your triangle count gets to high, you have to find the complex 3D-Asset in your scene, to see the triangle count of a single object, search the Asset in the asset-window and click on the mesh as seen below: 
![](images/trianglecountsingleobject.gif)
You can now see the triangle count in the inspector: 
![](images/trianglecountsinsingleobject.jpg)

To reduce the triangles of an object, you can use a 3D-modelling-software like blender, you can find more information here: 
[Simplify a Mesh in Blender](https://all3dp.com/2/blender-simplify-mesh-simply-explained/)


# <a name="light"></a>Lighting the Scene
![](images/lights.jpeg)

## Realtime Lights 
Realtime lights calculate the lightrays in realtime, that means you can move the lights, move the object that catch shadows from the light without any prerendering. 

There are three types of lights: Spotlight, Pointlight, Directional ligth

## Baked Lights
For more advanced lighting you can bake your light, that means you prerender your lightmap which is then like a fixed texture on the object. You can't move the light source or the objects that get illuminated without recalculating the light. 

Two examples for baked lights are: area lights and skyboxes. 

To see the effect of a baked light, you have to set the object to static which you want to illuminate: 
Select the object in the hierarchy and select Static -> Contribute GI 

![](images/staticlighting.jpeg)

Then go to the "Lighting"-window (Window -> Rendering -> Lighting) and click on "Generate Lighting" (make sure the "Auto-Generate"-Box is not ticked)

## Skyboxes 
Skyboxes can be used to very easily create a complex lighting (and background) for a scene. It's basically a sphere around the scene that is filled with a texture, that illuminate the scene. 

To use a skybox go the lighting window (Window -> Rendering -> Lighting) and select the skybox material: 
![](images/skyboxlighting.jpeg)

(Note: You have to click on "Generate Lighting" and your Objects need to be static)

Best places to find skyboxes: 
- [Polyhaven](https://polyhaven.com/hdris)
- [Unity Asset Store](https://assetstore.unity.com/2d/textures-materials/sky)

### Importing a skybox (from Polyhaven)
Download the skybox as .exr (i would recommend 4k resolution, if you wanna see the skybox in the background, if not 1k should be enough). 

Import to Assets, then select the image in the Project Window and go to the inspector and select texture shape -> 
![](images/importsettings.jpeg)

Then create a material (Assets -> Create -> Material) go the inspector and search for "Cubemap" in the shader dropdown. 
![](images/skyboxmaterial.jpeg)

Then you can drag and drop the image that you imported in the cubemap area. 
![](images/skyboxmaterial2.jpeg)

Now you can use the skybox in the lighting settings. 


# <a name="audio"></a>Audio 

To add sound to a scene create a new Audio Source: GameObject -> Audio -> Audio Source. Or drag and drop your soundfile in the Sceneview. 
![](images/AudioSource.gif)


- [Tutorial: Sound Component in Unity](https://learn.unity.com/tutorial/working-with-audio-components-2019-3)

Supported file formats: 
- AIFF 
- WAV 
- MP3
- Ogg 

Places to get (free) sounds: 
- [Adobe Creative Cloud](https://www.adobe.com/products/audition/offers/AdobeAuditionDLCSFX.html)
- [Unity Asset Store](https://assetstore.unity.com/?category=audio&free=true&orderBy=1)
- [freesounds.org](https://freesound.org/people/Nox_Sound/)
- [OpenGameArt](https://opengameart.org/art-search-advanced?field_art_type_tid%5B%5D=13)
- [Soundcloud](https://soundcloud.com/)

> Tutorial how to work with Audio Tracks in the timeline: [Unity Learn: Audio and the Timeline](https://learn.unity.com/tutorial/working-with-audio-tracks-in-timeline#5f6126e3edbc2a0020034db9)

## <a name="spatialaudio"></a>Spatial Audio

Spatial Audio works in Unity out of the box. If you have created an audio source in unity, you can use the "Spatial Blend" value to set how much the positioning of the audio source affects the volume and audible direction of the source. 
![](images/Audio1.jpg)

With "Min Distance" and "Max Distance" you can set the minimum and maximum distance of audibility. 
![](images/Audio2.jpg)

With the "Volume Rolloff" you can select different Rolloff algorithms. Select "Linear Rolloff" if you want to hear a strong difference based on the positioning, "Logarithmic Rolloff" for a more realistic effect. 
![](images/Audio3.jpg)

# <a name="animation"></a>Animation: Timeline
![](images/animations.jpeg)

## Animations window 

To animate an object, open the "Animation" window (Window -> Animation -> Anmation). 
Then select the GameObject you want to animate in the hierarchy window, now you should see this in the Animation Window: 
![](images/beginanimating.jpeg)
Click on "Create" this creates an *Animation Clip*.

Now you can start to animate your object either by hitting the record button:
![](images/record.gif)
or by manually adding the properties and keyframes: 
![](images/keyframe.gif)

See also:
- [Tutorial Animation in Unity](https://learn.unity.com/tutorial/working-with-animations-and-animation-curves#)

By default the Animation will loop, if you only want it to play once select the Animation Clip in the Project window and untick "Loop Time" in the Inspector. 
![](images/loop.jpeg)


> This method works best when you want to animate a single objects, like a spinning light. If you want to animate multiple objects together and the timing is importing, like for example a cinematic scene, or a transition scene then the "Timeline"-feature works better. 

## Animator window
![](images/Animator.jpeg)

*Note: we don't need the animator window for our course, but it's easier to understand the Unity Animation system if you know about it* 
The Animator selects when your animation clips will be played, for example when you want to create a Character that has different states (like walking, standing, running) and one animation clip for each state you would animate this in the Animator window (in general: non-linear animations). In this case you would need a little bit of coding, you can find a tutorial here: 
https://www.youtube.com/watch?v=tveRasxUabo

## Timeline
![](images/Timeline.jpeg)

The Timeline works best if you want to create a linear sequence of animations, like a transition scene or a little movie sequence. 

To work with the Timeline open the Timeline window (Window -> Sequencing -> Timeline). 
Then create an empty GameObject (GameObject -> Create Empty) and name it "Director", this GameObject will control our movie sequence (and also our cameras later). 

> You can click on the settings wheel on the upper right side and choose whether you wanna work in seconds or in frames. ![](images/timing.jpeg)

### Activating Objects in the Timeline
With the timeline you can easily activate and deactivate objects. Right-click on the left side of the Timeline window and select "Activation Track" then drag and drop the GameObject you want to activate and deactive in the selector field. 
![](images/activation.gif)
You can also change the time when and for how long your object should be active
![](images/changeactivation.gif)

### Animate Objects
You can also animate object in the same way as in the Animation window, but in the Timeline window you can directly see the timing for the whole scene, in case the animation should happen at a specific point in time. 
Right click on the left side again and select "Animation Track" (always make sure that the "Director" GameObject is selected in the hierarchy) then drag and drop the object you want to animate in the selector field and click on record. 
![](images/animationtimeline.gif)

> Here you can find some information about the other tracks you can use with the timeline: [Overview of the Timeline-Features](https://lukeduckett.medium.com/it-all-comes-down-to-timing-a-quick-guide-to-timeline-in-unity-fd96b26820f4),[Control Track](https://christopherhilton88.medium.com/what-is-a-control-track-in-timeline-f70588662cce), [Signal Track](https://blog.unity.com/technology/how-to-use-timeline-signals), [Playable Track](https://docs.unity3d.com/2018.3/Documentation/ScriptReference/Timeline.PlayableTrack.html)



