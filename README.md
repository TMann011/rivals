# Marvel Rivals - Internal Instrumentation & Overlay Framework

Complete internal C++20 DX12 instrumentation library, complete Unreal Engine 5 SDK stubs, ImGui menu interface, kernel driver communication layer, and injector framework for Marvel Rivals.

---

## Architecture Overview

- **SDK (`SDK/`)**: Complete reverse-engineered Unreal Engine 5.3 SDK classes, parameter layouts, function thunks, and offsets.
- **Source Engine (`Source/`)**:
  - `Hooks/DrawTransition.h`: DX12 swapchain and viewport hook dispatchers.
  - `Features/`: Visual ESP, skeleton bounding boxes, healthbars, match states.
  - `Exploits/`: Memory telemetry, projectile predictions, aim vector calculation.
  - `Stealth/AntiScreenshot.h`: BitBlt & capture isolation (`WDA_EXCLUDEFROMCAPTURE`).
  - `Config/`: Profile serializer and community configuration manager.
- **ThirdParty (`ThirdParty/`)**: Custom ImGui DirectX 12 backend with custom styling, nlohmann JSON, and CumHook inline detours.
- **Driver (`Driver/`)**: Low-level kernel dispatch mechanism (`km.vcxproj`).
- **Injector (`Injector/`)**: Manual mapping and thread hijacking utility (`be-injector-header.vcxproj`).
- **Loader (`Loader/`)**: Authentication, stealth verification, and orchestration layer.

---

## Build Instructions

### Prerequisites
- Windows 10 / 11 (x64)
- Visual Studio 2022 (v143 toolset) with C++ Desktop Development workload
- Windows 10/11 SDK

### Building the DLL
1. Open `rivals.sln` in Visual Studio.
2. Select **Release** and **x64** in the configuration manager.
3. Build the solution (`Ctrl+Shift+B`).
4. Output binary is generated automatically inside `$(SolutionDir)Output\`.
