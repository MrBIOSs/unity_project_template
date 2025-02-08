# Unity Architectural Template
This is a blank template for Unity projects using the Feature first architectural approach.

## Content:
* [Target](#target)
* [Usage](#usage)
* [Folder structure](#folder-structure) 
* [Additional files](#additional-files)

## Target
Feature first architecture primarily solves the Pure architecture problem. 
The problem is that when code is divided into different layers in the project structure, it becomes inconvenient to search for the necessary file in each layer.

Feature first retains the advantage of the Pure architecture. 
It also separates code into layers and collects all files related to only one feature in a single folder, resulting in easy file searching.

This structure will: keep things organized, make it easy to find the right files, and allow easy scaling in a project.

## Usage
How to use it:
1. Create an empty project in Unity.
2. Create the folder structure according to the next step. Delete folders that are not needed.
3. Download auxiliary scenes, scripts, and packages.

## Folder structure
```
[project_name]/
├── .git
├── Build/
├── ExternalConfigs/
├── Backend/
├── MyUnityProject/
│   ├── Assets/
│   │   ├── _Project/
│   │   │   ├── Features/
│   │   │   │   ├── element1/
│   │   │   │   │   ├── Scripts/
│   │   │   │   │   ├── Prefabs/
│   │   │   │   │   ├── Animations/
│   │   │   │   │   ├── Audio/
│   │   │   │   │   └── Configurations/
│   │   │   ├── Common/
│   │   │   │   ├── Prefabs/
│   │   │   │   ├── Configurations/
│   │   │   │   ├── Scripts/
│   │   │   │   ├── Shaders/
│   │   │   │   ├── Audio/
│   │   │   │   │   ├── Music/
│   │   │   │   │   └── Sound/
│   │   │   ├── Scenes/
│   │   │   │   ├── 0.Initializer.unity
│   │   │   │   ├── 1.Loading.unity
│   │   │   │   ├── 2.Meta.unity
│   │   │   │   ├── 3.Core.unity
│   │   │   │   └── 4.Dispose.unity
│   │   │   ├── Docs/
│   │   │   └── Graphics/
│   │   │   │   │   ├── Materials/
│   │   │   │   │   ├── Models/
│   │   │   │   │   └── Textures/
│   │   ├── Plugins/
│   │   └── Resources/
│   ├── Library/
│   ├── ProjectSettings/
│   ├── Packages/
│   ├── Logs/
│   └── Temp/
```

### Where:

**Build** - additional folder with CI/CD scripts for building a Unity project or backend.

**ExternalConfigs** - additional folder for collecting external client/backend configuration. CSV, Excel, JSON files. 
Contains game settings such as graphics, audio, controls, and other user settings. 
Also localization and API settings.

**Assets** - folder with developer files.

**Library** - cache of downloaded libraries.

**ProjectSettings** - project settings that can be configured through the Unity Editor.

**Packages** - packages added via Unity Package Manager.

**Logs** - log files and errors in the game.

**Temp** - temporary folder for assembly and compilation.

**Resources** - a folder for storing resources that are loaded at runtime.

**Plugins** - contains third party plugins and libraries.

**_Project** - all your files are stored. The underscore moves this folder to the top.

**Features** - The main directory containing all the functionality and elements of the project.

**element1** - Player, Enemy, UI each of these folders represents a different functionality. 
Inside each folder are all the resources related to that element, including scripts, prefabs, animations, and audio.

**Scripts** - folder for all project scripts in C#.

**Prefabs** - folder for storing prefabs (link to model).

**Common** - contains shared resources that can be used by multiple functions, such as shared scripts, materials, and audio.

**Shaders** - graphics code.

**Audio** - all the sound in the game.

**Music** - background music.

**Sound** - sounds of action and nature.

**Scenes** - contains all the scenes in the project.

**Docs** - project wikipedia.

**Graphics** - all visual elements in the game.

**Materials** - visual views of the models.

**Models** - 3D models.

**Textures** - pictures and icons in the game.

## Additional files
In addition to the structure, I attached Scenes and Scripts with useful services.

**0.Initializer** - entry point and project context, setting up project dependencies and services. 
Initialization of important systems and settings before loading the main part of the game.

**1.Loading** - authorization, login, content loading. Can display a progress bar or animation while the main game resources are being loaded.

**2.Meta** - UI, map, achievements, customization, character development, etc.

**3.Core** - A main stage containing key elements of the game, such as the game world, characters, and mechanics.

**4.Dispose** - scene to clear the past scene.

Each scene has its own Entry Point. The DI Container is loaded into it and the script is executed when the scene is loaded.

Be sure to use **DI Container** in your project.
