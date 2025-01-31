# <a name="photogrammetry"></a>Photogrammetry

Two apps i tested and work good:

- [Polycam](https://apps.apple.com/de/app/polycam-lidar-3d-scanner/id1532482376)
- [Luma AI](https://apps.apple.com/de/app/luma-3d-capture/id1615849914)

> Note: Often 3D scanned models are very detailed and Unity can't handle the data very well. To make sure that Unity can handle the models, you can decimate your 3D-Models in the 3D-Software Blender, you can find a Tutorial here: https://www.youtube.com/watch?v=N4QY-1Vf6LM 

# <a name="camera"></a>Camera & The Game Window

## Camera
![](images/camera1.jpeg)
The Camera in Unity acts as the player’s view into the game world, rendering everything it sees. It defines what is visible on screen, including perspective, depth, and field of view. Every Unity scene starts with a Main Camera, which you can find in the Hierarchy panel. You can adjust its properties in the Inspector, such as position, projection type (perspective or orthographic). In the scene view you can also see the cameras view frustum and a small preview of what the camera sees. 
When you are in the scene view you can right click on the camera and choose "Align to View", this aligns the camera to your current scene view.

## Game View
The Game View window in Unity shows how your game will look when played. It renders what the Main Camera sees and simulates the final player experience. You can test gameplay, adjust resolutions, and switch between different aspect ratios. The Play, Pause, and Step buttons allow you to run and debug your game in real time. Unlike the Scene View, which is for editing, the Game View provides a preview of the final visuals and interactions. 
![](images/camera2.jpeg)

When we work with Animations and Audio you can only see and hear the effect with the game running, to do this, click the Play-Button on top of the window: 
![](images/camera3.jpeg)

> !!! Changes made in Play Mode are not saved, so be sure to stop the game by clicking the Play button again before making any adjustments. !!! 


# <a name="visualeffects"></a>Visual Effects & Global Volume

The Global Volume in Unity is a component that applies post-processing effects across the entire scene. You can adjust settings like exposure and color adjustments in a Volume Profile to control the overall look of your game. Since it affects the whole scene, it’s useful for setting up consistent visual aesthetics. 

To change the settings select "Global Volume" in your hiearchy, in the inspector you can see the different settings. If you click on "Add Override" you can add effects. 
![](images/visualeffects.jpeg)

> If you don't have a Global Volume Game Object in your scene you can add it when you go to: GameObject -> Volume -> Global Volume

Some of the effects are: 
- Chromatic Aberration – Simulates lens distortion by slightly separating colors, creating a fringing effect often seen in real-world camera lenses.
- Color Adjustments – Allows control over brightness, contrast, saturation, and hue to fine-tune the overall color balance of the scene.
- Depth of Field – Blurs objects based on their distance from the camera, mimicking how real cameras focus on specific areas.
- Film Grain – Adds a subtle grainy texture to simulate the look of old film cameras, enhancing a cinematic feel.
- Lens Distortion – Warps the edges of the image to mimic real-life lens imperfections, often used to create a fisheye or wide-angle effect.
- Lift, Gamma, Gain – Provides fine control over color grading by adjusting shadows (lift), midtones (gamma), and highlights (gain).
- Motion Blur – Blurs objects based on their speed and direction, creating a smoother, more dynamic look for fast movements.
- Shadows, Midtones, Highlights – Separately adjusts the brightness and color of different tonal ranges, offering advanced control over lighting and contrast.

> You can find a detailled Tutorial here: [POST PROCESSING in URP (Universal Render Pipeline)](https://www.youtube.com/watch?v=oXNy9mszKxw)

# <a name="audio"></a>Audio 

To add sound to a scene create a new Audio Source: GameObject -> Audio -> Audio Source. Or drag and drop your soundfile in the Sceneview. 
![](images/AudioSource.gif)


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

> - [Tutorial: Sound Component in Unity](https://learn.unity.com/tutorial/working-with-audio-components-2019-3)


## <a name="spatialaudio"></a>Spatial Audio

Spatial audio in Unity simulates how sounds change based on their position relative to the listener, creating a more immersive experience. It takes into account distance, direction, and environmental effects to make sounds feel like they are coming from specific locations in 3D space.

### Audio Listener & Audio Sources

- The Audio Listener component, usually attached to the Main Camera, represents the player's "ears" and determines how sound is perceived in the scene. Only one Audio Listener should be active at a time.
- Audio Sources are attached to GameObjects that produce sound. They determine volume, pitch, spatial blend, and 3D positioning of the audio.
![](images/Audio1.jpg)

With "Min Distance" and "Max Distance" you can set the minimum and maximum distance of audibility. 
![](images/Audio2.jpg)

With the "Volume Rolloff" you can select different Rolloff algorithms. Select "Linear Rolloff" if you want to hear a strong difference based on the positioning, "Logarithmic Rolloff" for a more realistic effect. 
![](images/Audio3.jpg)

# <a name="video"></a>Video 

Unity can handle a variety of video format for playback in the scene, you can find the list here: [file format Unity Video](https://docs.unity3d.com/Manual/VideoSources-FileCompatibility.html). In my experience the H264 format in the .mp4 container works best. 

Importing videos is straightforward: just drag and drop them in your project window, like all other assets. 

To render the video in the world space you need a "virtual screen", for example a Quad that you position in your scene. You can then drag and drop your video on the squad and Untiy will add the Video Player component automatically. 
Its best to scale the Quad according to your video aspect ratio, otherwise the video will be distorted. 

When you select the GameObject with the video attached you can change settings like whether the video loops, the playback speed or the volume.
![](images/video1.jpeg)

> By default the sound of the video plays directly over your speakers. To get more control you change the Audio Output Mode to "Audio Source" and add a Audio Source: ![](images/video2.gif)


# <a name="animation"></a>Animation
![](images/animations.jpeg)

Unity’s Animation system allows you to bring objects to life by animating their properties over time using keyframes. The Animation Window is used to create and edit animations by setting keyframes at different points on a timeline.

- Keyframes – Snapshots of a property at a specific time. Unity smoothly transitions between them.
- Animation Clips – A sequence of keyframes that define an animation (e.g., a door opening, a character jumping).
- Animator Component – Controls animation playback on a GameObject.
- Animation Controller – Manages transitions between multiple animations.

What can be animated easily?

Unity allows you to animate nearly any GameObject property, including:
- Transform Properties – Position, rotation, scale (e.g., moving a platform up and down).
- Visibility – Enabling/disabling objects (e.g., making an enemy appear).
- Light Properties – Intensity, color, range (e.g., flickering torch effect).
- Material Properties – Color changes, etc.

What can't be a easily? 
- The form of the mesh itself, so deforming the mesh. For this, the best way is to rig you figure in the 3D-Software Blender, you can find a tutorial here: [Rigging for impatient people](https://www.youtube.com/watch?v=DDeB4tDVCGY)

## Animations window 

To animate an object, open the "Animation window" (Window -> Animation -> Anmation). 
Then select the GameObject you want to animate in the hierarchy window, now you should see this in the Animation Window: 
![](images/beginanimating.jpeg)
Click on "Create" this creates an *Animation Clip*.

Now you can start to animate your object either by hitting the record button:
![](images/record.gif)
or by manually adding the properties and keyframes: 
![](images/keyframe.gif)

After you have created your Animation click on "Play" to see the animation in your Game View. 

By default the Animation will loop, if you only want it to play once select the Animation Clip in the Project window and untick "Loop Time" in the Inspector. 
![](images/loop.jpeg)

> See also:
- [Tutorial Animation in Unity](https://learn.unity.com/tutorial/working-with-animations-and-animation-curves#)
- You can also create 2D Animations with this system, you can find a detailled Tutorial here: [Introduction to Sprite Animations](https://learn.unity.com/tutorial/introduction-to-sprite-animations#)


## Animator window
![](images/Animator.jpeg)

*Note: In the next session we will have a look how we can change animations in the animator window* 
The Animator selects which of your animation clips will be played. For example when you want to create a Character that has different states (like walking, standing, running) and one animation clip for each state you would animate this in the Animator window (in general: non-linear animations). 

# <a name="characters"> Characters

In this session we will implement a character that can walk through the scene controlled by our mouse and keyboard input. We will work with the third-person-perspective, but first person would also be possible. A first-person perspective lets the player experience the game through the character’s eyes, with the camera positioned as if they are seeing directly from their head. This is creating an immersive but limited field of view. A third-person perspective shows the character from behind or at an angle, allowing the player to see their full body while moving providing better spatial awareness.

For the implemtation we will use this plugin from the Unity Asset Store: https://assetstore.unity.com/packages/essentials/starter-assets-character-controllers-urp-267961 

> The Unity Asset Store is an online marketplace where developers can find and purchase assets to use in their Unity projects. It offers a wide range of resources, including 3D models, textures, animations, scripts, sound effects, and complete game templates. Both free and paid assets are available. 

To install the asset, sign in with your Unity Account and click on "Add to my Assets". 

Afterwards click on "Open in Unity", in Unity click on Download and then Import. 
![](images/Asset1.jpeg)
Unity will now ask you whether you want to install the dependencies, click on "Install/Upgrade" and after that click on "Yes" when it asks you about the new Input System this will restart your Unity Editor. 
![](images/Asset2.jpeg)

Now we have to import the package, open the Package Manager (Window -> Package Manager), select "My Assets" and search for "Starter Assets: Character Controllers".
![](images/import1.gif)

Now you should see a folder "Starter Assets" in your project window. In this folder go to Runtime -> ThirdPersonController -> Prefabs and drag and drop the "NestedParentArmature_Unpack.prefab" in your scene and adjust the position. 
![](images/import2.gif)

> Prefabs in Unity are reusable GameObjects that store a predefined configuration, including components, properties, and child objects.

Now deactivate your Main Camera, since the Prefab already has a camera. 
![](images/import3.gif)

When you now click Play, you should be able to control the Character with your keyboard and mouse. 
![](images/import4.gif)

## Changing the character 

If you want to change the character, you have to options: 
	- choose another humanoid character (e.g. from Mixamo)
	- use another 3D Model, which is not animated (note: you can also animate this in theory, but we won't cover this in this course)

### Choose another humanoid character

You can find a lot of free to use characters at [Mixamo](https://www.mixamo.com), you can also create your own scanned character e.g. with [Avaturn](https://avaturn.me/) or [in3D](https://in3d.io/) (unfortunately not for free). 

For this course we will use Mixamo, so login and go to the characters tab and select a character. 
![](images/mixamo1.jpeg)

And download them in T-Pose as a fbx for Unity:
![](images/mixamo2.jpeg)

Then import the .fbx to Unity and select the file in the Project window. We first fix the textures like this: 
![](images/mixamo3.gif)

And then import the rig (the movable bones) like this: 
![](images/mixamo4.gif)

Now we can change the Avatar, in the scene for this go to the NestedParentArmature_Unpack Prefab in the scene and show the child-objects with clicking on the arrow on the left side. And also show the child-objects of PlayerArmature:
![](images/mixamo5.gif)

> Child Objects in Unity are GameObjects that are hierarchically linked to another GameObject, called the Parent. When a Parent Object moves, rotates, or scales, its Child Objects inherit those transformations.

Then make the imported .fbx-file a child object (drag and drop it into the hierarchy) of PlayerArmature and deactivate the old Avatar with deactivating "Geometry" and "Skeleton"
![](images/mixamo6.gif)

The last step is to select the PlayerArmature Object and change the Avatar to the current Avatar (the Object with the same name as your imported .fbx). 
![](images/mixamo7.gif)

### Choose another 3D Model 

To choose another 3D Model as a character, we first need to delete the old prefab which uses a humanoid rig. So select "NestedParentArmature_Unpack" in the hierachy and select "Delete" after a right click. 

Then we can import our new rig, you can find it under StarterAssets -> Runtime -> ThirdPersonController -> Prefabs -> NestedParentCapsule_Unpack. Drag and Drop this in your hierarchy or scene and position it correctly. 

Now we have a capsule moving in the same way as the humanoid character before: 
![](images/3dmodelcharacter1.gif)

Now we can change the Model in a similar way, open the Prefab again and deactivate the "Capsule"-object: 
![](images/3dmodelcharacter2.gif)

Then drag and drop the Object you want to use as a Character in the hiearchy directly beneath the "Capsule"-object and position and scale it accordingly: 
![](images/3dmodelcharacter3.gif)

Now you can move around with you 3D-Object as a Avatar/Character in your scene: 
![](images/3dmodelcharacter4.gif)

## First Person Controller 

To use a first person controller, you can use the FirstPersonController-Prefab, you can find it under: Starter Assets -> Runtime -> FirstPersonController -> Prefabs -> NestedParent_Unpack. Drag and Drop in your Scene hierarchy and change the position according to your scene. 
![](images/firstperson.jpeg)

### Changing Camera perspective

You can also change the camera perspective in your third & first person controller, like the height or the distance to the Avatar. 

To do this open the Prefab and search for a object called "PlayerFollowCamera", in the inspector you can now find different parameters to change: 
![](images/positionavatar_1.jpeg)

- Vertical FOV, the Field of View of the Character or Camera 
- In the "Body" section you can change the positioning: 
	- change the height, distance and in general the position with the Shoulder Rig Offset parameters
- in the "Noise" section you can add different forms on noise applied to the camera, the default setting is the noise of a handheld camera. 
![](images/positionavatar_2.jpeg)

# <a name="dialogue">Dialogue System 

Next we will create a simple dialogue system. Simple means, that you can only go to through a list of sentences and not choose different answer options etc. 

For this we will use the Dialogue System Plugin from HeneGames: [Dialogue System in the Asset Store](https://assetstore.unity.com/packages/tools/gui/dialogue-system-248969)

Just like when installing the Controller Asset before, click on "Add to my Assets" and then "Open in Unity". In the Unity package manager click on "Download" and "Import".

After importing, you should see a Folder called "HeneGames" in your Project window. In the folder go to Dialogue System -> Prefabs, here you can find all the necessary prefabs. 
![](images/dialogue1.jpeg)

## Creating the first dialogue

We first need to include the User Interface, for this drag and drop the "Dialogue UI" in your hierachy.

Next we can create the object with which the character should interact, for this we drag and drop the "Dialogue 3D"-Prefab in the scene. 

This is the object which triggers the dialogue system, when the character enters, so you can place this where you want the dialogue to start. 
When you select the Dialogue 3D-GameObject you can see a green box around it in the scene view, this marks the area when the dialogues starts when the characters comes near: 
![](images/dialogue2.jpeg)
You can change this size in the Box collider size section. 

> A Collider in Unity is a component that defines the physical shape of a GameObject for collision detection. It allows objects to interact with each other by detecting overlaps and preventing them from passing through one another. Colliders can be basic shapes (Box, Sphere, Capsule) for efficiency or Mesh Colliders for detailed accuracy. When combined with a Rigidbody, colliders enable physics-based interactions, such as bouncing, sliding, or triggering events.

With the trigger state you can change whether the dialogue starts when the characters just enters the collider or whether the player has to press a key first: 
![](images/dialogue3.jpeg)

In the sentences section you can now add your dialogue sentences. You can also add some audio files which will be played when the dialogue is visible. 
![](images/dialogue4.jpeg)

> You can also activate certain events when a dialogue is played (in the Sentence Event () field) or also when the dialogue starts or end (Start Dialogue Event()).

## Creating Dialogue Characters

You can display a character's name when the dialogue is activated.

To create a new character in the plugin, navigate to Assets → Create → Dialogue Systems → New Dialogue Character. 
![](images/dialogue5.jpeg)

This will generate a new asset, which you can rename in the Inspector.
![](images/dialogue6.jpeg)

Next, go to Dialogue 3D and drag and drop the created asset into the Dialogue Character field to assign it.
![](images/dialogue7.jpeg)

## Changing the behaviour and look of the dialogue system 

When you select the Dialogue UI GameObject in your hiearchy you can change the look and some of the behaviour of the dialogue system. 

E.g. you can change the key to trigger the dialogue and go to the next sentence: 
![](images/dialogue8.jpeg)

To change the look of the dialogue window open the Dialogue assets GameObject, here you can find all of the elements you can then deactivate the ones you don't need (e.g. the portrait), resize them, change the color etc. 
![](images/dialogue9.jpeg)

> You can find a tutorial how to work with the UI system in Unity here: https://medium.com/coinmonks/introduction-to-ui-elements-in-unity3d-b2c8701e378b#a3cf

> To change the font you need to import your font first, for this you can find a tutorial here: https://docs.unity3d.com/Packages/com.unity.textmeshpro@4.0/manual/FontAssetsCreator.html



