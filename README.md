# Arma 3 / CSWR: Controlled Spawn & Waypoints Randomizr v6.5
>*Dependencies: none.*

CSWR is an Arma 3 script that allows the Mission Editor to spawn AI units and vehicles (by ground or air paradrop) and makes those groups move randomly to waypoints forever in life, where spawn-points and waypoints are easily pre-defined by Mission Editor through Eden marker's positions. CSWR accepts faction loadout customization, including additional customizations for sniper teams and paratroopers. CSWR almost doesn't change any original Arma AI behavior, saving server performance and Arma 3 integrity.

Creation concept: bring life to the mission through non-stop units' movements with some level of unpredictability without losing control of server performance and what AI units can do.
Special thanks: To the old (but gold) "T8 Units" script for the inspiration over the years.

## HOW TO INSTALL / DOCUMENTATION

video demo: https://www.youtube.com/watch?v=gcnvC2-qAFs

Video install: https://www.youtube.com/watch?v=vTz8v2cgrQQ

Documentation: https://github.com/aldolammel/Arma-3-Controlled-Spawn-And-Waypoints-Randomizr-Script/blob/main/controlled-spawn-and-waypoints-randomizr.stratis/CSWRandomizr/_CSWR_Script_Documentation.pdf

__

## SCRIPT DETAILS

- No dependencies from other mods or scripts;
- Manually define which markers the faction can use as spawn-points;
- NEW! - Sectorize which groups can spawn through many sectorized spawn-point options of their faction;
- Create unlimited different types of spawn-points (including air paradrop) for one or more factions;
- Spawn-points can be triggered by mission starts, Timer delay (down count), Trigger activation, and Target status (unit killed or building destroyed);
- Once the spawn-points are created, the script will spawn the groups randomly through their faction spawns (sectorized or not);
- There's no re-spawn. Death is death for units and vehicles spawned by CSWR; 
- Vehicles with turrets spawned by CSWR, when damaged, their gunners will try to never leave the vehicle, doing the last standing in combat;
- Manually define which markers will be used as one type of destinations (waypoints) for AI units and vehicles;
- There are 4 types of destinations: move, watch, hold, and occupy;
- Once the destination markers are created, CSWR will take care of taking (or not) the groups there, randomly;
- NEW! - Sectorize which groups can move through many sectorized destination options of their faction;
- Manually set the number of soldiers, who they are, their loadouts, who belongs in each squad type, and even ground vehicles and helicopters;
- Add or remove Night-Vision-Goggles and Flashlights for one or more factions, easily through "True" or "False" management;
- There are 7 infantry templates and 8 vehicle templates to customize (with modded or original content) for each faction; 
- Define easily how many AI groups are in-game, what squad types they belong, and their behavior: safe, aware, stealth, combat, chaos;
- All vehicles and units spawned by CSWR can be (ON/OFF) editable by Zeus;
- Set if the CSWR should wait for another script load first on the server;
- Debugging: Mission Editor has a friendly error handling;
- Debugging: Mission Editor has a hint monitor to control some AI numbers during the tests;
- Debugging: full documentation available.

__

## IDEA AND FIX?

Discussion and known issues: https://forums.bohemia.net/forums/topic/237504-release-controlled-spawn-and-waypoints-randomizr/

__

## CHANGELOG

**Nov, 25th 2023 | v6.5**
- Fixed > Sectorizing > Now is forbidden to sectorize the moviment "_move_ANY" because it doesn't make sense at all;
- Fixed > Occupy > When the mission editor hid a building, the group still considered that building as a possible location to occupy;
- Fixed > Occupy > An error (caused only in v6.0) when the group leader kicked an unit out of the group if the unit was too far from them;
- Improved > Occupy > Now groups are able to occupy big towers like Military Cargo Towers;
- Improved > Occupy > If the building is a ruin, and its type is an accepted one, the group when into it will stay in a crouch to units get a lower profile on it;
- Improved > Occupy > Expanded the amount of forbidden buildings and acceptable ruins based of Western Sahara DLC map;
- Improved > Occupy > Expanded the amount of forbidden buildings and acceptable ruins based of Global Mobilization DLC maps;
- Improved > Occupy > If a building is badly added by Editor as forbidden and acceptable building at the same time, CSWR in debug mode will point this;
- Documentation has been updated.

**Nov, 14th 2023 | v6.2**
- Fixed > Ocuppy > Occupy-destination-markers weren't working fine when they were sectorized;
- Fixed > Missions with respawn system applied were hidden CSWR markers even when debug mode was True (init.sqf updated);
- Fixed > When a group (spawned in a sectorized spawn) assigned with _move_ANY destination command without sector declared to destination too, an error was printed out;
- Improved > Watch > Now, if the sniper group doesn't find any peak or hill, they will search for secondary high places (mounts);
- Improved > Waiting time for the next vehicle spawn when it's been used spawn delay for that decrease from 10 to 1 second;
- Improved > Unit classnames from other sides are accepted and converted automatically to the mission editors' side choice;
- Hotfix 11th > Fixed a typo in "fn_CSWR_globalFunctions.sqf" (line 3587) that was printing out an error specific if only sectorized spawns were dropped on the map, without any non-sectorized ones (Thanks to reporting, VR_NotKilled);

**Oct, 25th 2023 | v6.0**
- Added > Markers scan > Now CSWR knows how to sectorize spawns and destinations, so Editor can define which groups and vehicles must consider those sectors or not;
- Added > Vehicles > When a vehicle's lost but its crewmen survive, if allies are close, the crew will join them, taking their mission to themselves;
- Fixed > Paradrop > Civilian parachuters are landing without stuck in crouched position (panic);
- Fixed > Debug > Small fix about marker message's examples;
- Fixed > Occupy > Vehicles configured to use Occupy-move markers were able badly to try to occypy a building;
- Improved > Helipcoter > Besides the regular move to the waypoint, now helicopter has 33% of chance to approach the current waypoint with Seek & Destroy style;
- Improved > Hold > Small improvement during the hold maneuver validation when solid objects around and group leader is out of the vehicle;
- Improved > Hold > Civilian tracked-vehicle cannot booked center marker position anymore as a tank or trackedAPC;
- Improved > Destinations > All infantry and vehicles are able to restore their waypoints (doing a new search) if they are accidentally deleted;
- Improved > Markers scan > Small improvements;
- Documentation has been updated.

**Oct, 11th 2023 | v5.5**
- Added > Spawn for helicopters can be set over the ship floors or platforms in water. Check the documentation;
- Added > All infantry soldiers and paratroopers can get easily flashlights on their rifles when the editor desactivates their night-vision-goggles;
- Improved > All CSWR markers are invisible since the Briefing screen (init.sqf file has been included in project);
- Improved > New method (more feasible to performance) to check if destinations and spawn-points are busy before accept new groups/vehicles, avoiding accidental explosions;
- Improved > Loadout > New method to build custom loadouts (more flexible and intuitive);
- Improved > Loadout > The global options to force apply backpack and/or vest for all units now will ignore civilian faction;
- Improved > Hold > New method to turn the tracked vehicle to hold-marker direction even more accurate and safe (against vehicle bounces);
- Improved > Hold > When in debug-mode-global is TRUE with debug-hold-mode is also TRUE, now the hold-markers and its direction are visible to the Mission Editor in-game;
- Improved > Spawn delay > from now the spawn delay timer is configured in-minutes and not in-seconds anymore, making the Mission Editor's life easier;
- Improved > Loadout > Now it's possible to turn On or Off which faction will get nightvision and what nightvision device model (supports NVG from mods too);
- Improved > Loadout > Ue the "RANDOM" command in civilian uniform slot in loadout file to gives a random outfit for each CIV unit created by CSWR;
- Improved > Debug > Marker error handling has been improved;
- Fixed > Paradrop > If editor added a custom nightvision for paratroopers, they received it duplicated;
- Fixed > Paradrop > Infantry Sniper groups when got the paratroop speciality and had their backpack "REMOVED", they weren't receiving parachutes;
- Fixed > Loadout > When editor used the global loadout settings (CSWR_isBackpackForAllByFoot and CSWR_isVestForAll) civilians get army gears too;
- Fixed > Watch > Sniper group's killed before to reach their spot to watch a location, CSWR kept waiting for them inappropriately;
- Fixed > Helicopters > They weren't spawn in the same direction defined through the Eden spawn-markers;
- Fixed > Wheeled APC and tracked APC crewmen were not receiving custom crew helmet;
- Removed > Civilian faction cannot move to anywhere ("_move_ANY" instruction) like a soldier, from now it's been limited to public markers ("_move_PUBLIC");
- Documentation has been updated.

**Sep, 18th 2023 | v5.1**
- Fixed > CRITICAL > In CSWR v5.0, all AI groups were stuck after the first waypoint to be completed;
- Fixed > Hold > In CSWR v5.0 the tracked-vehicles accidentaly stopped to execute correctly the hold-maneuver;
- Improved > Performance > BIS_fnc_spawnGroup method has been replaced by a saver server performance method;
- Improved > Performance > BIS_fnc_spawnVehicle method has been replaced by a saver server performance method;
- Improved > Paradrop > Paratroopers are executing the paradrop with much more space among each other (visual realistic);
- Improved > Paradrop > Paratroopers are regrouping with their leaders after the landing and before the first mission move on the field;
- Improved > Loadout > Paratroopers can receive helmet and nightvision customization separately from the regular faction loadout;
- Improved > Vehicles > Now it's possible turn off the Electronic Warfare Resources for vehicles of each faction in fn_CSWR_management.sqf file;
- Improved > Vehicles > UAV vehicles are blockers too if around the helipads if some helicopter will spawn; 
- Documentation has been updated.

**Sep, 13th 2023 | v5.0**
- Added > All factions can spawn helicopters (cswr_spawnheli_faction_1);
- Added > All factions can be spawned by Air Paradrop, including vehicles (cswr_spawnparadrop_faction_1);
- Added > Special customization for AI units executing the Air Paradrops;
- Added > Exclusive Spawns for helicopters have automatic insertion of helipads (ON/OFF);
- Improved > Each spawn-point-type has a list of AI group-type allowed to spawn there;
- Improved > Hold-move markers now delete all small stones around them to preserve tracked-vehicles maneuver integraty;
- Improved > Loadout customization received deeper and friendly debug messages;
- Improved > Vehicles will spawn facing super accurate the same direction set in their spawn-markers in Eden;
- Fixed > Main CSWR script folder name on GitHub was accidentaly named as .VR instead of .STRATIS;
- Fixed > A faction group shouldn't spawn in another faction spawn-points if the Mission Editor would force it;
- Fixed > If snipers didn't find out spots to prone, the WATCH_MOVE wasn't restarting properly;
- Fixed > Since the last update (v4.5), loadout customization stops to recognize the "removed" instruction when in lowcase;
- Fixed > Debug > Hold-move should have [1800,3600,7200] as minimal range of time, and not [1800,7200,10800];
- Fixed > Debug > Watch marker minimal range should be 1000, and not 500;
- Documentation has been greatly updated.

**Sep, 5th 2023 | v4.5**
- Added > Now the spawn-points can be triggered by Timer delay, Trigger delay, and Target delay;
- Fixed > Occupy and Hold debug messages had a wrong trigger for the minimal value message alert;
- Fixed > When using Occupy-move the units had their speed behaviors badly replaced by the waypoint speed (always as "normal" instead of editor choices);
- Improved > If Occupy or Watch moves are used with vehicles (not allowed), now the vehicles and their crewmen are correctly deleted, leaving a warning message for the editor;
- Improved > Many debug improvements to fn_CSWR_population.sqf feedbacks and auto-fixing;
- Documentation has been updated.

**Jul, 22nd 2023 | v4.0.1**
- Fixed > Old backpacks were been dropped on the ground if those were replaced with a new one by the editor (fn_CSWR_globalFunctions.sqf file updated).

**Mar, 9th 2023 | v4.0**
- Improved > Not needed to synchronize manually spawns and destination markers between script file and Eden anymore;
- Improved > Each group (troops and vehicles) restores the preset behavior configured by the Editor after each new destination is reached;
- Improved > Uniform, vest and backpack have a new function called "REMOVED" that allows the editor, for any reason, to spawn all their units with no those things;
- Improved > Groups (troops and vehicles) set as "be_STEALTH" now operate on "White" combat mode (Hold Fire but Engage At Will) and not "Green" anymore (Hold Fire and disengage);
- Improved > The file fn_CSWR_spawnsAndWaypoints.sqf has been renamed to fn_CSWR_management.sqf;
- Added > Vehicles and soldiers can (or not) spawn separately with specific spawn-points for faction vehicles;  
- Added > Sniper teams have their own loadout customization (uniform, vest, rifle, ammo, optics, and its attachments); 
- Added > Watch movement exclusively for sniper teams (_move_WATCH) makes the team associated look for high spots to stay overwatching the markers on the map until the mission ends, with no new moves;
- Added > Occupy movement for troops (_move_OCCUPY) makes the team associated occupy some building in a range, moving to the next one after a pre-defined time by the editor;
- Added > Occupy movement has a blacklist of building types and locations that troops must ignore;
- Added > Hold movement allows troops and vehicles to hold their position for a long time. Tracked vehicles have priority, staying in the center of the marker, looking almost exactly to the marker direction configured by the editor;
- Added > Each faction in the game can get its global formation easily customized. There are 2 presets for each faction. 

**Feb, 11th 2023 | v3.2**
- Improved > If the mission editor sets spawn-point markers or destination markers out of the map, they get a warning and the marker is ignored;
- Added > Included more options to customization vehicle composition (from 3 types to 6);

**Feb, 9th 2023 | v3.0**
- Added > Added an option that the mission editor sets a timer before the CSWR starts to run;
- Added > Included more options to customization infantry composition (from 3 templates to 6);
- Fixed > A huge server performance killer has been fixed (the script was running in background without spawn-points on map);
- Fixed > spawn-point markers are not visible anymore when debugging mode if off;
- Improved > Added a massive, friendly and automatic errors handling to CSWR, helping a lot the mission editor;
- Improved > Lot of code reviewing;
- Documentation has been updated.

**Jan, 20th 2023 | v2.8**
- Improved > You can define through fn_CSWR_loadout.sqf file a custom helmet for infantry and other only for heavy armored crewmen;
- Documentation has been updated.

**Oct, 18th 2022 | v2.7**
- Fixed > Crewmen were not getting customized loadout;
- Improved > fn_CSWR_debug.sqf file has been merged with fn_CSWR_spawnsAndWaypoints.sqf one;
- Improved > Now, mission editor has a specific file to customize their AI units: fn_CSWR_loadout.sqf;
- Improved > Loadout function is much more reliable to custom;
- Documentation has been updated.

**Oct, 14th 2022 | v2.6**
- Added > Now you also can customize the vest and backpack of each faction spawned through the CSWR Script;
- Added > Vehicles with turrets spawned by CSWR, when damaged, its gunners never leave the vehicle, staying in combat until the death;
- Added > All units and vehicles spawned by CSWR now are editable by Zeus in-game when Zeus is allowed in the mission;
- Documentation has been updated.

**Aug, 10th 2022 | v2.5**
- Now it's possible to customize the loadout for each spawned faction;
- Documentation has been updated.

**Jul, 14th 2022 | v2.1**
- Added "Stealth" as an option for spawned units/vehicles;
- Improved the vehicle creation, now each vehicle has its electronics/signals configured when available;
- Improved the Editor option to turn On and Off a faction;
- Documentation has been updated;

**Jul, 8th 2022 | v2**
- Fixed vehicles spawn problems when a lot of them;
- Fixed infantry could not walk properly if in "safe" behavior;
- A bunch of performance improvements;
- Documentation has been included;
- initServer.sqf has been removed.

**Feb, 22nd 2022 | v1.5.5**
- Fixed for dedicated servers: now the script is called through description.ext function and not more initServer.sqf execVN;
- Improved: automatic setMarkerAlpha for destination and spawn-point markers;
- Adjustment: function names.
- Removed "waitUntil" for player.

**Feb, 10th 2022 | v1.2.1**
- Zeus now can see all units and vehicle spawned of the script;
- Fix the missing global and private variables declaration;
- Map changed from VR to Stratis for honest testing results.

**Feb, 3rd 2022 | v1.0**
- Hello world.
