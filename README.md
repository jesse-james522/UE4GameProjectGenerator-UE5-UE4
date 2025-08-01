# UE4GameProjectGenerator
Small commandlet for generating a complete project using UE4SS header dump, Project File and Plugin Manifest

# Usage
Compile the project for the Development Editor Win64 target first
Make sure to add plugins your game depends on to the .uplugin file!

Run through the command line:
```
UE4=
"${ENGINE_DISTRIBUTION_BIN}\UE4Editor-Cmd.exe" "${PROJECT_DIR}\GameProjectGenerator.uproject" -run=ProjectGenerator -HeaderRoot="${HEADER_DUMP_PATH}" -ProjectFile="${GAME_PROJECT_FILE}" -PluginManifest="${GAME_PLUGIN_MANIFEST}" -OutputDir="${OUTPUT_DIR}" -stdout -unattended -NoLogTimes
UE5= 
"${ENGINE_DISTRIBUTION_BIN}\UnrealEditor-Cmd.exe" "${PROJECT_DIR}\GameProjectGenerator.uproject" -run=ProjectGenerator -HeaderRoot="${HEADER_DUMP_PATH}" -ProjectFile="${GAME_PROJECT_FILE}" -PluginManifest="${GAME_PLUGIN_MANIFEST}" -OutputDir="${OUTPUT_DIR}" -stdout -unattended -NoLogTimes
```
Where:
- ENGINE_DISTRIBUTION_BIN - path to the binaries directory of your local UE4 distribution
- PROJECT_DIR- path to the root of this project
- HEADER_DUMP_PATH - path to the root directory of UHTHeaderDump, generated from your game through UE4SS
- GAME_PROJECT_FILE - path to the .uproject file of your game (can be extracted from game paks)
- GAME_PLUGIN_MANIFEST - path to the .upluginmanifest file of your game (can be extracted from game paks)
- OUTPUT_DIR - path to the output directory for the resulting project (must exist)

For CMD:

:: Set environment variables (safe with spaces)
set "ENGINE_DISTRIBUTION_BIN=...\..\UE_MAJORVERSION.MINORVERSION\Engine\Binaries\Win64"
set "PROJECT_DIR=E...\..\UE4GameProjectGenerator"
set "HEADER_DUMP_PATH=...\..\UHTHeaderDump"
set "GAME_PROJECT_FILE=...\..\.Uproject"
set "GAME_PLUGIN_MANIFEST=...\..\.upluginmanifest"
set "OUTPUT_DIR=...\....\UEProjcetFolder"

Resulting project might need few edits to compile correctly.
