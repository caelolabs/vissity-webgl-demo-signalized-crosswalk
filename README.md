# Vissity
Vissity lets you visualize PTV Vissim traffic and PTV Viswalk pedestrians in Unity. Import network objects from a network file (.inpx), simulated vehicle traffic from a vehicle record file (.fzp), simulated pedestrian traffic from a pedestrian record file (.pp), and signal timings from a signal changes protocol file (.lsa). With Vissity, you can create highly realistic animations, visualizations, and immersive experiences with your simulated traffic. Go to the [Vissity page on the Unity Asset Store](https://assetstore.unity.com/packages/tools/integration/vissity-193837) to learn more and get Vissity.

[![Introducing Vissity](http://img.youtube.com/vi/f0Z_Ej8tT4E/0.jpg)](http://www.youtube.com/watch?v=f0Z_Ej8tT4E "Introducing Vissity 1.0.0: Visualize PTV Vissim traffic and PTV Viswalk pedestrians in Unity")

## Demos:
[This WebGL demonstration](https://caelolabs.github.io/vissity-webgl-demo-signalized-crosswalk/index.html) shows a "skeleton" build of a signalized crosswalk. (In this context, a skeleton build means that the links, signal heads, and vehicles are primitive GameObjects.) The purpose of this demonstration is to exemplify the synchronicity between the Traffic Manager and Signal Changes Manager. In this example, there are two Traffic Managers: one spawns vehicles that follow trajectories in a vehicle record file (.fzp) and the other spawns pedestrians that follow trajectories in a pedestrian record file (.pp). The Signal Changes Manager reads a signal changes protocol file (.lsa) with a signal controller of type VAP and is responsible for changing the signals.

Use "+" and "-" on your keyboard to increase and decrease the simulation speed factor by 1, respectively. Reversing time is possible.

This example is included in the Vissity package.

# Technical Details
## Key Features:
- The Time Controller component allows you to speed up, slow down, pause, and reverse the simulation.
- The Network Importer component parses a network file (.inpx) and imports PTV Vissim network objects as primitive GameObjects in Edit Mode. Currently, the following network objects can be imported: link segments, desired speed decisions, priority rules (stop lines), stop signs, and signal heads.
- A Materials List is a data container that is assigned to a Network Importer component. It defines which materials the Network Importer should apply to the PTV Vissim network objects when they are imported in Edit Mode.
- The Traffic Manager component reads trajectory data from a vehicle record file (.fzp) or a pedestrian record file (.pp) and facilitates the smooth animation of traffic in Play Mode.
- A Traffic Assets List is a data container that is assigned to a Traffic Manager component. It defines which prefabs the Traffic Manager should spawn for the PTV Vissim vehicle types or PTV Viswalk pedestrian types in Play Mode.
- The Signal Changes Manager component reads a signal changes protocol file (.lsa), loads traffic signal timings for each signal group from all signal controllers, and creates a field for each signal state. Each field can be assigned one or more mesh renderers in Edit Mode. In Play Mode, this component activates and deactivates the mesh renderers to animate traffic signal changes. This component supports a variety of signal controller types: Fixed Time, Built-in, VAP, Ring Barrier Controller (RBC), and more.

## Setup:
LTS Unity versions are recommended for stability (2019.4.x or 2020.3.x). In a Unity project, import the Vissity package. Navigate to **GameObject > Caelo Labs > Vissity**. Alternatively, right-click in the Hierarchy and select **Caelo Labs > Vissity**. A GameObject named Vissity is created with a Quick Start Guide component attached. Four child GameObjects are additionally created, each with a correspondingly named component attached: (1) TimeController, (2) Network Importer, (3) Traffic Manager, and (4) Signal Changes Manager.

Vissity takes advantage of custom inspectors wherever possible, which provide clear instructions every step of the way.

## Project Settings Requirements:
- API Compatibility Level .Net 4.x

## Support, Feedback, and Community:
If you need support, have feedback, or would like to engage with an active community of Vissity users, join our Discord server. For details, see the last page of the documentation or the Quick Start Guide component.

## Disclaimer:
- Vissity does not include source code.
- Vissity does not include game ready assets (vehicles, traffic elements, etc.). The Prefabs folder contains vehicles and a pedestrian created with primitive GameObjects to demonstrate how vehicles and pedestrians should be set up to work with Vissity. The Unity Asset Store has a large number of assets, some of which are free, that can be used in conjunction with Vissity.
- Vissity does not include a license for PTV Vissim or PTV Viswalk.
- Vissity does not offer a co-simulation feature with PTV Vissim or PTV Viswalk.
- End user is responsible for ensuring that no license agreements are violated in their use of Vissity.