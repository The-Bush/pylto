# pylto
pylto is a python script which generates a pdf of LTO tape labels for printing onto Avery label sheet 6577

Forked from: https://github.com/manic-software/pylto


# Usage
Run the executable located at `./dist/pylto.exe` to open the GUI

Command line arguments are currently deprecated in favor of the GUI.

# Dev
While developing, use `poetry` to manage dependencies and for testing. Test by executing:
```
poetry run python .\pylto
```
# Build
Pylto uses `pyinstaller` to generate an executable file.
After initializing with `poetry`, generate a new release `.exe` by running:
```
poetry run pyinstaller .\pylto --onefile
```
This will generate a new portable .exe in the `dist` directory