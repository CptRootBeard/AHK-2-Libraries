# AHK-2-Libraries
Contains my public libraries for use with AHK 2. All scripts use the *\*.ahk2* extension, so change extensions as needed.

I currently use a somewhat unique AHK project structure, but I'm looking for an easy way to make this structure cross-compatible with AHK's built-in library include system.

```
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

\*\*I do most of my library development in Notepad++, and have some macros I've recorded to convert #lib(someLibFolder) and #src(someSrcScript) into the appropriate includes.
I also use \_include.ahk2 to list any FileInstalls I need.

There is a file called standard-includes.ahk2 in the lib\ root that is included to start with on any actual project I make.
