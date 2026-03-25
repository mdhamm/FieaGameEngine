# FieaGameEngine

A C++ gameplay/engine foundation library built around a **data-driven object model** (Attributed/Scope/Datum), **runtime type information (RTTI)**, **factories**, **events**, and a simple **GameObject + Action + Reaction** composition system.

This repository is primarily a **library + test suite**. It’s organized as a Visual Studio solution with a static library target and a comprehensive set of unit tests.

## What’s inside

Core systems (all implemented in `source/Library.Shared/`):

- **Custom containers & utilities** (e.g., `Vector`, `SList`, `HashMap`, hashing/equality helpers)
- **Reflection-like data model** (`RTTI`, `Attributed`, `Signature`, `Datum`, `Scope`)
- **Factories** for string-driven creation of types
- **JSON parsing** via a coordinator/helper pattern
- **Event system** (`Event`, `EventQueue`, subscribers, attributed event messages)
- **Gameplay composition** (`GameObject`, `Action*`, `Reaction*`, `GameTime/GameClock`)

## Projects / solution layout

- `build/FieaGameEngine.sln` — Visual Studio solution entry point.
- `source/Library.Desktop/` — Windows static library project (toolset `v143`).
- `source/Library.Shared/` — Shared engine source (imported into the desktop project via `.vcxitems`).
- `source/Library.Desktop.Tests/` — Unit tests using **Microsoft::VisualStudio::CppUnitTestFramework** plus JSON test data files.
- `build/Shared.props` — Shared MSBuild property sheet used by the projects.

## Build (Windows)

### Prerequisites

- Visual Studio 2022
- Workload: **Desktop development with C++**
- Windows 10/11 SDK (Visual Studio installer will provide this)

### Build in Visual Studio

1. Open `build/FieaGameEngine.sln`
2. Select configuration/platform (e.g. `Debug | x64`)
3. Build the solution

### Build from the command line

From a “Developer Command Prompt for VS 2022”:

```bat
msbuild build\FieaGameEngine.sln /m /p:Configuration=Debug /p:Platform=x64
```

## Run tests

- In Visual Studio: **Test Explorer** → Run All
- Or: build the `Library.Desktop.Tests` project and run tests from within Visual Studio.
