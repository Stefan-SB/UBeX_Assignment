
# UBeX Assignment

## Getting Started
Use [Unreal Engine (5.4.4)](https://www.unrealengine.com/en-US/download) (uses Visual C++ 19.38) and [Visual Studio (2022)](https://visualstudio.microsoft.com/vs/). 
Required plugins are [Meta XR Unreal Plugin](https://developers.meta.com/horizon/downloads/package/unreal-engine-5-integration/71.0) and [Meta XR Platform Unreal Plugin](https://developers.meta.com/horizon/downloads/package/unreal-5-platform-sdk-plugin/71.0), and optionally [Visual Studio Integration Tool](https://learn.microsoft.com/en-us/visualstudio/gamedev/unreal/get-started/vs-tools-unreal-install) plugin from the Epic Games Launcher.
This project utilizes the [Meta Quest 3](https://www.meta.com/en-gb/help/quest/10004693912934783/?srsltid=AfmBOork_4NQHwrIOoAwDoBly_Baoes0xZYtWGWUrCKpZb3FwNphPPke) VR headset.


## Project Directory
The following describes the main directories and files in this project:

```
ubex-assignment/
├── Config/                                 # Project configuration files
├── Content/                                # Main UE content folder
│   ├── BPs/                                # Blueprints
│   │   ├── BP_Bike                         # Bicycle Blueprint (spawnable bike for the player)
│   │   ├── BP_StreetSuburban               # Blueprint for endless generating street
│   │   └── ...                             # Other blueprints
│   ├── Fab/                                # Additional assets
│   ├── FirstPerson/                        # First Person logic
│   │   ├── Blueprints/                     # First Person Blueprints
│   │   │   ├── BP_FirstPersonCharacter     # Player character Blueprint
│   │   │   ├── BP_FirstPersonGameMode      # Game mode Blueprint
│   │   │   ├── BP_FirstPersonController    # Player controller Blueprint
│   │   │   └── BP_PawnManager              # Manages which pawn is spawned
│   │   ├── Input/                          # First Person Input mapping and actions
│   │   │   ├── Actions/                    # Input action definitions
│   │   │   └── IMC_DefaultFP               # First Person Input Action Mapping
│   ├── FirstPersonArms/                    # First Person assets
│   ├── NPCs/                               # NPC folder
│   │   ├── Assets/                         # NPC assets
│   │   │   ├── Animations/                 # NPC animations (walking, cycling, etc.)
│   │   │   └── Models/                     # NPC models
│   │   ├── BPs/                            # NPC blueprints
│   │   │   └── BP_NPC                      # Biking NPC blueprint
│   ├── StarterContent/                     # Starter Assets
│   ├── StreetAssets/                       # Street-related assets
│   ├── UI/                                 # User Interface
│   │   ├── Misc/                           # Miscellaneous UI Assets
│   │   ├── WDs/                            # UI Widget Blueprints
│   │   │   ├── WD_BikingUI                 # UI Widget for main screen
│   │   │   └── WD_Menu                     # UI Widget for the UI test menu
│   ├── Vehicles/                           # Vehicle-related content
│   │   ├── Bicycle_With_Animations/        # Bike assets
│   │   └── Input/                          # Player Vehicle Input Controls
│   └── BikingScene.umap                    # Main Level
├── NPC_Assignment.uprojet                  # UE project file
└── README.md                               # This file
```

### Coding Challenge 1: NPC Cycling Behaviour (online)
**Objective:** 
Implement intelligent and realistic cycling behaviour for NPCs that dynamically interact with the player.
[📄 View the full assignment PDF](Docs/Assignment1.pdf)

**Relevant files/folders:**
- `NPCs/BPs/BP_NPC` – NPC Blueprint to implement logic and behaviour.  
- `NPCs/Assets/Animations/` – NPC animations (cycling, walking, etc.).  
- `BPs/BP_StreetSuburban` – Endless street generator (use for NPC destinations).  
- `FirstPerson/Blueprints/BP_FirstPersonCharacter` – Player character Blueprint (for player detection).  

**Player Biking Controls**
  - To start biking, approach the spawned bike on the bike lane. A text prompt will appear to press **'E'** to hop on.
  - Controls (rudimentary and unrealistic, intended only for testing): **'W'** to move forward (no acceleration or deceleration), **'A' / 'D'** to slightly drift left or right (no proper turning).
  - Press **'Tab'** to switch from first-person to third-person view.

**Street & Destination Handling**
  - `BP_StreetSuburban` handles endless street generation: when the player is within **240m** of the street end, it spawns another **120m** segment.
  - Ensure the NPC target destination (end of bike lane) works with continuous street generation.

You are free to use any approach in solving this challenge. You are allowed to modify any existing features if you think it's necesary in achieving the objective.

### Coding Challenge 2: VR Level Transformation (on site)
**Objective:** Convert the first-person level into a fully functional VR experience, preserving existing features while adapting UI and controls for VR.
[📄 View the full assignment PDF](Docs/Assignment2.pdf)

**Relevant files/folders:**
- `FirstPerson/Blueprints/BP_FirstPersonCharacter` – Player character Blueprint.  
- `FirstPerson/Blueprints/BP_FirstPersonGameMode` – Game mode (set in World Settings).  
- `FirstPerson/Blueprints/BP_FirstPersonController` – Player controller Blueprint.  
- `FirstPerson/Blueprints/BP_PawnManager` – Pawn manager (handles player pawn).  
- `UI/WDs/` – UI Widgets (must be adapted for VR interaction).  

You are free to use any approach in solving this challenge. You are allowed to modify any existing features if you think it's necesary in achieving the objective.

