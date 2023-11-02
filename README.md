# Project 1: Tekno

## Overview

**Tekno** is a project where I had the opportunity to work on various aspects of game development. My contributions spanned level design, environmental Lighting, VFX (Visual Effects), and platform scripting.

For detailed information about the level design and VFX work I undertook, please refer to my portfolio at [Tekno Portfolio](https://brandonsurin8.wixsite.com/website/tekno).

## Platforming

### Moving Platform

The [`PlatformMove`](https://github.com/qiuji10/Tekno/blob/b35cd453d5fcd61f4fdc85e49ce8b23c962ef7e2/Assets/3_Scripts/Platform/PlatformMove.cs#L67-L108) script is designed to control the movement of a platform in a game. This script is associated with the Koreographer plugin and is compatible with Unity. It handles the synchronization of platform movement with musical events, creating dynamic and rhythmic gameplay experiences.

### Script Components

- **Moving Platform Settings**: The script features various settings to control the platform's behavior, including the specification of an 'eventID' that correlates with a musical event in Koreographer. The script also manages an array of 'points' that represent the positions the platform can move to.

- **Koreography Sync with Stance Manager**: The script interacts with the Koreographer plugin and the Stance Manager to synchronize platform movements with specific musical genres. It dynamically adjusts 'eventID' and 'scaleFactor' based on the music's genre.

- **IPlatform Interface**: This script implements the 'IPlatform' interface, which defines platform behavior in the game. It allows for interaction with players and tracks player presence on the platform.

- **OnMusicEvent Function**: This function is triggered when a musical event occurs. It advances the platform to the next position in the 'points' array in sync with the music's beat.

- **Update Function**: The script continually updates the platform's position based on its movement, making sure the platform moves smoothly to the next point.

- **Beat Indicator**: I worked on the beat indicator for these platforms to create an engaging gaming experience.

### Beat Indicator On Platforms 

The [`BeatIndTest`](https://github.com/qiuji10/Tekno/blob/b35cd453d5fcd61f4fdc85e49ce8b23c962ef7e2/Assets/3_Scripts/Platform/BeatIndTest.cs#L59-L122) script is designed to manage the synchronization of materials in response to the rhythm of a song. It works in conjunction with the Koreographer plugin in Unity and cycles through a predefined array of materials, ensuring that the materials change based on the music's rhythm. The script is specifically designed to handle music with 4 beats, of which all tracks in Tekno share the same rhythm style.

### Script Components

- **Beat Settings**: The script allows you to set an 'eventID' that corresponds to a musical event in Koreographer. It also manages a `MeshRenderer` component named 'indicatorMesh,' which represents the object's visual appearance.

- **Stance Materials**: The script maintains a set of materials, including 'baseMat,' 'houseMat,' 'technoMat,' and 'electroMat.' These materials are used to represent different visual states and are synchronized with the musical events.

- **Material Cycling**: The script tracks the current material index and switches between materials in response to the music. When it reaches the end of the material array, it resets to the beginning, ensuring a continuous cycle of materials.

- **Stance Change Handling**: The script interacts with the Stance Manager to dynamically adapt its behavior to the genre of the music. It registers for specific events based on the musical genre.

- **OnMusicEvent Function**: When a musical event occurs, this function is triggered. It evaluates the event's integer payload and changes materials accordingly. The script also resets the previous material to its base state.

### Car Platform 

The [`PlatformMover`](https://github.com/qiuji10/Tekno/blob/b35cd453d5fcd61f4fdc85e49ce8b23c962ef7e2/Assets/3_Scripts/Platform/Testing%20Platform%20Visualization/PlatformMover.cs#L1-L51) script is designed to control the movement of a car platform in a game. It is attached to individual GameObjects representing the cars, and each car can be assigned a specific index in the Unity Inspector. The script operates in synchronization with a game's rhythm to create dynamic and engaging car platform movement.

### Script Components

- **Serialized Fields**: The script utilizes serialized fields to specify a list of `Transform` objects named 'points' and an 'index' value. These fields are accessible and configurable in the Unity Inspector.

- **Event Subscription**: During the `Awake` phase, the script subscribes to the `OnBeat` event provided by the `TempoManager`. This event is triggered at the game's rhythm. Upon `OnBeat`, the script checks if the `beatCount` is equal to 4, initiating the `MoveLogic` coroutine.

- **MoveLogic Coroutine**: The `MoveLogic` coroutine controls the movement of the car platform. It calculates the new position for the car by linearly interpolating between the current position and the target position defined by the 'points' list. This movement is synchronized with the game's tempo to ensure smooth motion.

- **Index Management**: After moving, the 'index' value is incremented. If it exceeds the number of points in the list, it is reset to 0 to cycle through the positions.


## Misc

In the "Misc" section, I handled various tasks, including:

- **[Buildings Color Sync Change](https://github.com/qiuji10/Tekno/blob/b35cd453d5fcd61f4fdc85e49ce8b23c962ef7e2/Assets/3_Scripts/MusicSystem/BuildingColorChange.cs#L34-L64)**: I was involved in synchronizing color changes for in-game buildings based on the current stance of the player.
- **[Billboard Cycling](https://github.com/qiuji10/Tekno/blob/b35cd453d5fcd61f4fdc85e49ce8b23c962ef7e2/Assets/3_Scripts/MusicSystem/BillboardCycle.cs#L63-L108)**: I managed the cycling of billboards that change according to beat in the game for a more immersive environment.

# Project 2: Swan Blindly

In **Swan Blindly**, my primary contributions were centered around level design and art-related tasks. Notably, I played a significant role in:

- **Terrain Design**: I was responsible for crafting the terrain in the game, contributing to the game's visual aesthetics and gameplay experience.
- **UI Design**: I designed and implemented the user interface (UI) elements for the game, enhancing the overall user experience.

For a more detailed explanation of my work on **Swan Blindly**, please visit my portfolio at [Swan Blindly Portfolio](https://brandonsurin8.wixsite.com/website/swan-blindly).

## MainMenuController Script

The [`MainMenuController`](https://github.com/Vinnaeysh1507/Swan_Blindly/blob/0c4250966b6da9ef48bec900ced2a74d7683608f/Swan_Blindly/Assets/Brandon/Scripts/MainMenuController.cs#L1) script is a critical component of the main menu functionality in our mobile game project, "Swan Blindly." This script empowers players with a range of settings and options to personalize their gaming experience. It controls aspects related to volume, gameplay settings, graphics, and resolutions, allowing players to fine-tune their preferences.

### Script Components

- **Volume Setting**: The script manages audio volume settings, including a volume slider. It enables players to customize the audio experience, and their chosen volume level is stored for future game sessions.

- **Gameplay Settings**: The script allows players to adjust sensitivity settings, particularly relevant for controlling in-game interactions. Sensitivity preferences can be set through a slider, and these settings are persisted for consistent gameplay.

- **Graphics Settings**: The script offers control over visual quality and graphics-related settings. It includes a brightness slider, a quality level dropdown, and the ability to toggle full-screen mode. These preferences impact the game's visual presentation.

- **Resolution Dropdown**: A resolution dropdown is provided to accommodate various screen resolutions. Players can select their preferred screen resolution for an optimized gaming experience.

- **Resolution Handling**: The script interfaces with the screen resolutions available, allowing players to select their desired resolution. It intelligently identifies the current screen resolution and sets the resolution dropdown accordingly.

- **Confirmation Prompt**: A confirmation prompt is displayed when settings are applied, providing visual feedback to players.

## PostProcessingManager Script

The [`PostProcessingManager`](https://github.com/Vinnaeysh1507/Swan_Blindly/blob/0c4250966b6da9ef48bec900ced2a74d7683608f/Swan_Blindly/Assets/Brandon/Scripts/PostProcessingManager.cs#L1) script plays a role in managing post-processing effects and visual enhancements in our project. These effects contribute to the overall atmosphere of the game. This script is designed to handle various post-processing profiles dynamically, making it possible to transition between different visual styles and apply effects in response to in-game events.

### Script Components

- **Volume Profiles**: The script utilizes Unity's Volume framework to manage post-processing profiles. It allows for the seamless switching between different profiles, each of which defines a unique set of post-processing effects. These profiles can significantly impact the game's visual presentation.

- **Individual Post FX Values**: The script accesses specific post-processing effects within the chosen volume profile. This includes Vignette, Bloom, and Chromatic Aberration, each contributing to the visual experience.

- **Setting Variables**: The script incorporates various setting variables, such as `resetProfileTimer`, which controls the timing of profile transitions. These settings offer flexibility in managing the visual effects applied during gameplay.

