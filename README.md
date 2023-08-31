# Remnat2-FIX-Dx12-Linux

For Fix the error in Remnant II and other gammes that saids that dx12 is not supported by your card in linux, on lutris, bottles or steam in many games like insurgency sandstorm or Remnat2. 

## Requeriments
Need:
- Bottles (I prefer bottles than lutris for this example, is more secure and easy, i am using flatpak version)
- vc_redist of microsoft (Need it in the bottle or runner, download links bellow.)
- If you use a non original version and want play online lan need do this steps firts ([Online Fix for non original](https://www.reddit.com/r/LinuxCrackSupport/comments/tqjp3z/guide_running_steamworks_fixonline_fix_with_linux/)) and then continue reading this guide.
- If you use the original steam game, can start here
- ProtonUP-QT


Create a bottle or runner with whatever proton-ge it is not important for now
in my case my bottles is insurgencito (create by insurgency but now i'll use it for renmnat 2)
Located in: /home/noe/.var/app/com.usebottles.bottles/data/bottles/bottles/Insurgencito
Now install vc_redist in the bottle:
  - (x86) -> [https://aka.ms/vs/17/release/vc_redist.x86.exe](https://aka.ms/vs/17/release/vc_redist.x86.exe)
  - (x64) -> [https://aka.ms/vs/17/release/vc_redist.x64.exe](https://aka.ms/vs/17/release/vc_redist.x64.exe)
  - Install both files
  
  ![image](https://github.com/Milor123/Renmnat-2-FIX-Dx12-Linux/assets/14153649/f4fe9126-4a77-424c-9dbe-94ef28f7e76c)

## Add ProtonGE to steam

in the Renmnat case I'm using Proton-GE-8-13, installed with ProtonUP-QT

Important note for install Proton-GE versions:
you need download and extract Proton-GE manually or using ProtonUp-Qt (tool), but need stay sure that Steam detects your Proton-GE

By default in my ProtonUp-QT, it install the runners in ~/.local/share/Steam/compatibilitytools.d/ (STEAM DONT DETECT THIS IN MY PC)

In my case i need move or install direct the runners in
~/.steam/root/compatibilitytools.d/
![image](https://github.com/Milor123/Renmnat-2-FIX-Dx12-Linux/assets/14153649/c421d2ad-a2aa-4280-b7a7-31e579841eae)
My folder of the bottle is `/home/noe/.var/app/com.usebottles.bottles/data/bottles/bottles/Insurgencito` (this is the folder in bottles flatpak version, if you dont use flatpak, search the correct location)

## Create a virtual disk and link the compatdata and pfx
STEP 1 (only needed if you use a non original steam game) else Direct go to the Step 2

This step is probably the more hard. 

You need use the compatdata folder of a installed game or install un games

`/media/noe/Jouji/SteamLibrary/steamapps/compatdata/{ID-GAME}`

in my case i think use the insurgency steam compat folder (581320) for my Remnant II
Keep it in mind because we need add it in a enviroment variable

`STEAM_COMPAT_DATA_PATH=/media/noe/Jouji/SteamLibrary/steamapps/compatdata/581320`
if you need add the Env variable in non original games maybe could need it [ENV-Variable Oficial Docs](https://github.com/sonic2kk/steamtinkerlaunch/wiki/ENV-Variables)
its very easy, please read or try add it to the launch options, i am not sure if works too.

STEP 2 (if you have the original game)
you id should be the number 1282100
And this case we dont need create a enviroment variable, but if you dont found this folder, search in you game by your id
![image](https://github.com/Milor123/Renmnat-2-FIX-Dx12-Linux/assets/14153649/f30b3d25-f164-4095-92ee-def7e5a0bd54)

`STEAM_COMPAT_DATA_PATH=/media/noe/Jouji/SteamLibrary/steamapps/compatdata/1282100` using the 1282100 for your game, ignore my image number


STEP 3 (This is very very important for anything case)

Need move or delete pfx in the compatdata/ID-game/pfx folder for then create a link to the bottles
in the pfx contais the virtual disk informacition with the windows files.

for the non original games
sudo rm /media/noe/Jouji/SteamLibrary/steamapps/compatdata/{ID-SOMEONE-GAME}/pfx
sudo ln -s /home/noe/.var/app/com.usebottles.bottles/data/bottles/bottles/{yourBottleName} /media/noe/Jouji/SteamLibrary/steamapps/compatdata/{ID-SOMEONE-GAME}/pfx

For the original games 
sudo rm /media/noe/Jouji/SteamLibrary/steamapps/compatdata/1282100/pfx
sudo ln -s /home/noe/.var/app/com.usebottles.bottles/data/bottles/bottles/{yourBottleName} /media/noe/Jouji/SteamLibrary/steamapps/compatdata/1282100/pfx

note for both: (/media/noe/Jouji) is my HDD disk where is installed the game

If you doing all, now the game should run. Go to the game and select your Proton-GE runner, if you have something `vc_redist` error, need verify that the steam is loading correctly the STEAM_COMPAT_DATA_PATH or sure install in the correct bottles the vc_redist files

Enjoy!!!

