# Guide
ref: [GUIDE](https://developer.rhino3d.com/guides/rhinopython/ghpython-debugging/)
RHINO 7 ONLY!

## Installation
Iron Python is not supported anymore with templates by VS 2019 and next releases. So the guide above is partially valid.
Use the `debugger` project that I have created for you.

1. Install Visual Studio on your machine. For example VS Community.
1. Install Ironpython 2.7 on your machine [IRONPYTHON 2.7](https://ironpython.net/)
2. Install Python dev tools on your VS platform using VS Installer. More info here [PYTHON TOOLS](https://visualstudio.microsoft.com/it/vs/features/python/)
3. Open VS and Go to Debug > Options > Python > Debugging and tick Use Legacy Debugger
4. Open Rhino 7 and run _EditPythonScript to open the editor. In Tools > Options > Script Engine, tick the Frames and Tracing checkboxes
5. Change "vs_python_path" of config.json. You need to add path to your VS installation folder.

## How to use it
1. Change "vs_python_path" of config.json. You need to add path to your VS installation folder.
2. Run VS code using `debugger.sln`
3. Open the file `gh_debug.gh` with Rhino 7
4. Make sure both Rhino 7 and Grasshopper are opened
5. (VS) Place a break point on the line you want in `gh_debug.py` to start to debug
6. (VS) Go to Debug/Attact to Process, Select Connection Type Python Remote
7. (VS) Type `tcp://dev@localhost:2019/` on target and press `ENTER` of your keyboard
8. (VS) You should see the Rhino Process below, Select it and `Attach`

Now you can active and deactive the process for debugging using Debug/Attact to Process and Debug/Reattact to Process. You can also refresh grasshopper component to run the debugger again.

# Notes
Please, pay attention. I have copied/pasted code inside `gh_debug.py` changing the position of the inputs just to leave the special input free, `code`. Once the logic is fixed you can copy/paste only the useful parts inside the native `UserObject`