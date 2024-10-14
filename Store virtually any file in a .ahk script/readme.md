copy from https://www.autohotkey.com/board/topic/64481-include-virtually-any-file-in-a-script-exezipdlletc/

Store virtually any file in a .ahk script (or compiled .exe)
Download: Here
Current version: 2.6
Compatible with: AHK Basic, AHK L ANSI, AHK L Unicode (X86/X64)


File types i've tested and know work: .zip, .exe, .txt, .ahk, ...anything?

The .ahk size of the file is rougly 1.33x the normal filesize(s). The compiled .exe (without compression) is rougly 1-1.05x the included filesize(s).

If you find any bugs or have anything to suggest please feel free to post.




How to use!:
1. Download and save the .ahk to a directory of your choosing.
2. Run the script
3. Select a file you want to include with your script(s)
4. Enter a name for the function you call to recreate the file (valid function names only)
5. Wait for it to do its stuff
6. Answer the questions on how you want to save the script
7. Simply include the code via #include or pasting it into your script
8. Call the function with Extract_*name* and the path/name of the file you want it to save as and it will recreate the file

we need a script to extract the embedded code  ( save as Extract.ahk )
```ahk
#Include HelloWorld_Embedded.ahk

SplashTextOn 200, 200, Extracting, Please Wait...
Extract_HelloWorld_Embedded( A_ScriptDir "\HelloWorld_Extracted.ahk" )
while !FileExist( A_ScriptDir "\HelloWorld_Extracted.ahk" )
    Sleep 100
Sleep 1000
ControlSetText Static1, Done!, Extracting
Sleep 1000
SplashTextOff
ExitApp
```
Run Extract.ahk and if all went well you should now have HelloWorld_Extracted.ahk in your script dir. 
