# Project 1: Tekno

## Overview

**Tekno** is a project where I had the opportunity to work on various aspects of game development. My contributions spanned level design, lighting, environment creation, VFX (Visual Effects), and platform scripting.

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

### Car Platform 

The [`PlatformMover`](https://github.com/qiuji10/Tekno/blob/b35cd453d5fcd61f4fdc85e49ce8b23c962ef7e2/Assets/3_Scripts/Platform/Testing%20Platform%20Visualization/PlatformMover.cs#L1-L51) script is designed to control the movement of a car platform in a game. It is attached to individual GameObjects representing the cars, and each car can be assigned a specific index in the Unity Inspector. The script operates in synchronization with a game's rhythm to create dynamic and engaging car platform movement.

### Script Components

- **Serialized Fields**: The script utilizes serialized fields to specify a list of `Transform` objects named 'points' and an 'index' value. These fields are accessible and configurable in the Unity Inspector.

- **Event Subscription**: During the `Awake` phase, the script subscribes to the `OnBeat` event provided by the `TempoManager`. This event is triggered at the game's rhythm. Upon `OnBeat`, the script checks if the `beatCount` is equal to 4, initiating the `MoveLogic` coroutine.

- **MoveLogic Coroutine**: The `MoveLogic` coroutine controls the movement of the car platform. It calculates the new position for the car by linearly interpolating between the current position and the target position defined by the 'points' list. This movement is synchronized with the game's tempo to ensure smooth motion.

- **Index Management**: After moving, the 'index' value is incremented. If it exceeds the number of points in the list, it is reset to 0 to cycle through the positions.


## Misc

In the "Misc" section, I handled various tasks, including:

- **Buildings Color Sync Change**: I was involved in synchronizing color changes for in-game buildings.
- **Billboard Cycling**: I managed the cycling of billboards in the game for a more immersive environment.

# Project 2: Swan Blindly

In **Swan Blindly**, my primary contributions were centered around level design and art-related tasks. Notably, I played a significant role in:

- **Terrain Design**: I was responsible for crafting the terrain in the game, contributing to the game's visual aesthetics and gameplay experience.
- **UI Design**: I designed and implemented the user interface (UI) elements for the game, enhancing the overall user experience.

For a more detailed explanation of my work on **Swan Blindly**, please visit my portfolio at [Swan Blindly Portfolio](https://brandonsurin8.wixsite.com/website/swan-blindly).

## Main Menu
