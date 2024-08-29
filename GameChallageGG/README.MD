# GameHacking.gg

Welcome to the guide for reverse engineering and modding games. If you are already familiar with the tools, you may also want to do a cursory check of the game code in dnSpy as well. I disable the anti-cheat here before ever running the game at [gamehacking.gg](https://gamehacking.gg/). It was great to meet you guys at DEF CON! This is a great...

Use Cheat Engine and some kind of decompiler, like [Ghidra](https://github.com/NationalSecurityAgency/ghidra) or [dnSpy](https://github.com/dnSpy/dnSpy), to understand and modify the game code. C# assemblies are much easier to understand with these tools.

# ##Note

> #### I didn't know anything about creating games before, but I do know C/C++ and Python. I'm diving into game development now, and it's been quite a learning experience! 🙈
> 
> #### You can check out the awesome video for John Hammond on YouTube walkthrough : [Video](https://youtu.be/Y0O3SHrBFbE?si=lc80MUMy82FXmE59).
> 
> 

<span style="color:red;">Make Sure You Disabled AntiCheat</span>

# Levels

Guide for each level:

### [Level 1](level1.md)

### [Level 2](level2.md)

### [Level 3](level3.md)

### [Level 4](level4.md)

### [Level 5](level5.md)

### [Level 6](level6.md)

### [Level 7](level7.md)

### [Level 8](level8.md)

### [Level 9](level9.md)

#### Tools Overview

1. **dnSpyEx**:
   
   - This tool is great for decompiling, editing, and examining .NET assemblies, which are often used in Unity games.
   - After you install the Unity game, head to the `Managed` directory usually found at `GAMENAME\GAMENAME_Data\Managed`.
   - Drag and drop the `Assembly-CSharp.dll` file into dnSpyEx to dig into the game’s source code.
   - You can disable anti-cheat mechanisms by either stubbing out method bodies or modifying IL instructions. Pay special attention to methods like `Start`, `Update`, `GetHashOfCode`, and `IsCheatProcessRunning`.

2. **Cheat Engine**:
   
   - A robust debugger and memory viewer that's perfect for analyzing and tweaking the game while it's running.
   - Be cautious to skip any bundled adware during installation.
   - Customize hotkeys in Cheat Engine for faster memory scanning while playing: `F1` for Decrease Value, `F2` for Increase Value, `F3` for Changed Value, and `F4` for Unchanged Value.

## Reverse Engineering Process

- **Using dnSpyEx**:
  
  - Look for and modify the game's anti-cheat features. You can replace method bodies with stubs or adjust IL instructions as needed.
  - Don’t forget to save your changes by navigating to `File > Save Module`.

- **Using Cheat Engine**:
  
  - Utilize Cheat Engine to analyze and alter the game’s memory in real time.
  - Its capabilities, like tracking memory changes, are invaluable for debugging and adjusting game behavior.
