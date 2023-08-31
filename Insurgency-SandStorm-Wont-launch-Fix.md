I've fixed temporaly the crash and wont start, and the UAC with the next method.

### What need?:

1. Bottles
2. Game installed  -> on STEAM with Proton-GE 7-55 (ON STEAM)
3. Proton-GE or install manually the Runners (Proton-GE versions)

EDIT2: while was writing this post i've test and Proton-GE 8-13 works too

**Important note for install Proton-GE versions:** 
you need download and extract Proton-GE manually or using ProtonUp-Qt (tool), but need stay sure that Steam detects your Proton-GE

By default in my ProtonUp-QT, it install the runners in `~/.local/share/Steam/compatibilitytools.d/` (STEAM DONT DETECT THIS IN MY PC)

In my case i need move or install direct the runners in 
`~/.steam/root/compatibilitytools.d/`

![image](https://github.com/ValveSoftware/Proton/assets/14153649/c18697e0-7fb8-49cb-aab7-61ed7f88e333)

### Fixing the insurgency sandstorm bug that dont run in my ubuntu
for solve this bug, need help of lutris or proton, what for? I need create the virtual drive with the data

Need a folder like this, i recommend create it with bottles because its more easy and secure, in lutris you could lose games data or something in a accident.

Lutris version:
![image](https://github.com/ValveSoftware/Proton/assets/14153649/6105fbf9-2aaf-437e-a7dc-9aafa48a0978)

Bottles version (RECOMMENDED) (It will be create each a new bottle, this bottle was create with Proton-GE 8 but its in teory dont is important because we dont need use the GE files, only need the virtual disk configuration.)

/home/noe/.var/app/com.usebottles.bottles/data/bottles/bottles/Insurgencito
![image](https://github.com/ValveSoftware/Proton/assets/14153649/3fab6f12-a217-4661-8cb8-5463ce932087)

Now need create a link in the **pfx** folder of steam game where is installed game

in my case is 
/media/noe/Jouji/SteamLibrary/steamapps/compatdata/581320

Jouji is the hdd disk where i have the game
581320 is the Steam ID game (Insurgency Sandstorm)

for this case use:
mv  {folder+pfx} {folder+pfx.backup} (it moves the original pfx folder to other.backup)
sudo ln -s {bottlesfolder or lutris windows files folder} {folder+pfx}
example :
```
sudo mv  /media/noe/Jouji/SteamLibrary/steamapps/compatdata/581320/pfx  /media/noe/Jouji/SteamLibrary/steamapps/compatdata/581320/pfx.backup
sudo ln -s /home/noe/.var/app/com.usebottles.bottles/data/bottles/bottles/Insurgencito /media/noe/Jouji/SteamLibrary/steamapps/compatdata/581320/pfx
```

![image](https://github.com/ValveSoftware/Proton/assets/14153649/96fb9fed-0d93-438a-bba8-6c34b62b014f)

Now try open the game from steam, it should install the anticheat and other things.
The game should run now, try run it for 2 times again.
if it dont work or get bugged, delete the steam pfx folder and relink to the new bottle (create a new bottle)

### Dx12 or Directx12 wont run in Insurgency SandStorm (Fixed)

I was finally able to correct this error in the same way we corrected the error where the game wouldn't open or the anticheat was throwing an error.

Please read what I wrote previously in this same post.
NOTE: in DX12 version I get a anticheat kick xD 

### Enable ASYNC 

Use the enviroment **`RADV_PERFTEST=gpl`** if your proton is version **>=7-45**

If you proton is  version **less <= 7-45** need:
`DXVK_ASYNC=1`

For example of configuration in steam:
`RADV_PERFTEST=gpl %command% -nominidumps -USEALLAVAILABLECORES -NoGlobalInvalidation -dx12`
or
`RADV_PERFTEST=gpl %command% -nominidumps -USEALLAVAILABLECORES -NoGlobalInvalidation`  using dx11 as default (i prefer it because my proccesor is very old, a i7 4790k :/  )
