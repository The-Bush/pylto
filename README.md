# pylto
pylto is a python script which generates a pdf of LTO tape labels for printing onto Avery label sheet 6577

Forked from: https://github.com/manic-software/pylto


# Usage
Run the executable located at `./dist/pylto.exe` to open the GUI

## Fields:

(REQUIRED) LTOGeneration [1-10]

(OPTIONAL) Prefix
  - The prefix that will precede every number in the sequence.
  - ex. LTO
    
(REQUIRED) Numbers
  - The range of numbers to generate labels for.
  - ex. 1-100
    
(REQUIRED) Offset [>=0]
  - The number of labels to skip before starting to print

## Custom List mode
Toggle "Custom List" (instead of "Range") to print a specific set of labels rather than a generated
sequence. Enter one label per line, or comma-separated, e.g. `AB1234, CD5678`. Each entry:
  - Is used as typed (uppercased) for the label ID — no Prefix is applied and no zero-padding is
    added.
  - Still gets the selected LTOGeneration appended, exactly as in Range mode. Selecting generation 7
    turns `M26081` into barcode `*M26081L7*` with an `L7` generation box.
  - Must be 6 characters or fewer, using only characters supported by the barcode font
    (`0-9A-Z-. $/+%`).

Offset still applies in Custom List mode the same way it does in Range mode.

NOTE: Command line arguments are currently deprecated in favor of the GUI.

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
