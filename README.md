#QuitBit

* Owner- Joel Longanecker

* Essential Contributor- [MiRIr](https://github.com/MiRIr)
* Non-essential Contributor- [PlGGS](https://github.com/PlGGS)

2017

##Changelog:
2017-07-28 - Created actual C# project to compile C# 6 code. Added BringToFront feature to help prevent emulators from running in the background.
2016-02-16 - Added restore resolution flag. Some emulators do not play nice with big picture mode, and this is an attempt to fix this.

##About QuitBit

QuitBit is a simple, lightweight piece of software designed to act as an intermediary between a frontend and an emulator.
A long standing problem with setting up a mouse and keyboard free emulation system is stopping the emulator and returning to the frontend. QuitBit does that, and only that.

##Getting this software

* Download this File- [TopQuitBit.cs](https://github.com/PlGGS/quitbit/edit/master/TopQuitBit.cs)
* Open up cmd.exe
* Navigate to the folder where you downloaded QuitBit.cs
* Execute the Following- C:\Windows\Microsoft.Net\Framework\v4.0.30319\csc.exe /out:QB.exe QuitBit.cs
**Note that this does not work with v4.0 of the .NET framework, and that you must now compile with the latest version for C# 6!**

##Features

* Quits an emulator (or any other program)
* Simple integration into different frontends (ICE, EmulationStation, etc)
* Time argument that requires the button combination to be held for any specified amount of time

##Usage

Command     |Short Command|Purpose                                  |Example 
------------|-------------|-----------------------------------------|-------
--buttons   |--b          |Button combination to close the program  |--b=0+8+6
--load      |--l          |Full path to the executable to load      |--e=C:\Emulators\nes.exe
--controller|--c          |ID of specific controller to use         |--c=0
--time      |--t          |Milliseconds to hold down the combination|--t=2500
--params    |--p          |Parameters when launching the program    |--p=C:\roms\NES\Zelda.nes
--rr        |--rr         |Restore Resolution                       |

--load and --buttons are the only arguments that are required. If --controller is not used, it will check every controller plugged into the system.


* Standalone Usage Example
```
TopQuitBit.exe --buttons=1+2+4 --load=c:\emulators\dolphin\dolphin.exe --t=2000
TopQuitBit.exe --c=2 --b=2+0+1 --load=C:\Emulator Programs\NES\nestopia.exe --params=C:\Roms\Nintendo\Metroid.nes
```

* EmulationStation Usage Example

```
<systemList>
    <system>
         <name>genesis</name>
         <fullname>Sega Genesis</fullname>
         <path>C:\Roms\genesis</path>
         <extension>.bin .zip</extension>
         <command>TopQuitBit.exe --buttons=6 --load=c:\retroarch\retroarch.exe --params=-D -L C:\retroarch\cores\genesis_plus_gx_libretro.dll "%ROM_RAW%"</command>
         <platform>genesis</platform>
         <theme>genesis</theme>
    </system>
<systemList>
```
