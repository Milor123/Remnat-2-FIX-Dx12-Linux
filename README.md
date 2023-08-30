# Remnat2-FIX-Dx12-Linux

For Fix the eror that saids that dx12  is not supported by your card in linux, on lutris, bottles or steam in many games like insurgency sandstorm or Remnat2. 

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
