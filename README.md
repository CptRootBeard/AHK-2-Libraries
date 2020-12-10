# AHK-2-Libraries
Contains my public libraries for use with AHK 2. All scripts use the *.ahk2 extension, so change extensions as needed.

I am currently using a somewhat unique AHK project structure, though I am looking for an easy way to make this structure cross-compatible with AHK's built-in library include system.

```javascript
Project
  |
  |---- lib
  |     |---- someLibFolder
  |     |         |---- someScript.ahk2
  |     |         |---- <etc.>
  |     |         |---- lib.manifest.ahk2 (#include %A_LineFile%\..\someScript.ahk2, etc.)
  |     |
  |     |---- <etc.>
  |
  |---- src
  |     |---- someProjectSpecificScriptOrClass.ahk2
  |     |---- <etc.>
  |
  |---- _include.ahk2 (#include %A_LineFile%\..\lib\someLibFolder\lib.manifest.ahk2)
  |       **I use #lib(someLibFolder) and #src(someProjectSpecificScriptOrClass)
  |
  |---- main.ahk2 (#include %A_LineFile%\..\_include.ahk2)
```

\*\*I do most of my library dev. in Notepad++, and have some macros I've recorded to convert #lib(someLibFolder) and #src(someSrcScript) into the appropriate includes.
I also use \_include.ahk2 to list any FileInstalls I need.

I also have a standard-includes.ahk2 in the lib\ root that I start with on any actual project.
