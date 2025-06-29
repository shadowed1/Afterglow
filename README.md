<p align="center">
  <img src="https://i.imgur.com/vhqBIyM.png" alt="logo" width="5000" />
</p>  

### *Under active development. Bugs do exist.*

## *Run apps and games in Borealis using Flatpak for signficantly higher performance than Crostini!*
### Requirements: 

- ChromeOS
- Steam installed and open
- Internet connection
- Logging into Steam is NOT required.  
<br>
<br>

### How to install:

- Open Crosh (ctrl-alt-t) and type in: <br>
`vsh borealis`

- Copy Paste in borealis shell: <br>
`bash <(curl -s "https://raw.githubusercontent.com/shadowed1/Aurora/main/aurora_installer.sh?$(date +%s)")` <br>

*Aurora needs Borealis; it won't work elsewhere.*

<br>
<br>

### Features:

- Steam can be closed entirely as long as an app is running.
- Borealis shell tabs automatically initiate Flatpak support.
  
<p align="center">
  <img src="https://i.imgur.com/JaW6d3P.png" alt="logo" width="5000" />
</p>  

- Aurora can tweak display scaling and cursor size. 
- Fantastic hardware acceleration for all apps; even unsupported web browsers
- Built-in GPU acceleration allows for longer battery life vs software rendering.
- Minecraft Java with Prism Launcher @ 2160p:

<p align="center">
  <img src="https://i.imgur.com/SKNLuZb.png" alt="logo" width="5000" />
</p>  




### How to use:
Commands with examples:

`aurora                     # Show current display and cursor values` <br>
`source aurora display 1.0  # Set display scaling factor (0.25 - 4.0)` <br>
`source aurora cursor 32    # Set cursor size (8 - 200)` <br>
`aurora help                # Show help` <br>
`aurora_debug               # echo a list of paths that flatpak will use` <br>
`aurora reinstall           # Redownload Aurora from Github` <br>
`aurora uninstall           # Launch uninstaller` <br>

`flatpak list               # Show list of installed apps` <br>
`flatpak --help             # flatpak has a lot of commands!` <br>

NORMAL FLATPAK EXAMPLE:

`flatpak search Discord` <br>
`flatpak install com.discordapp.Discord` <br>
`flatpak run com.discordapp.Discord` <br>

Failed to connect to bus error it must be run like example below:

`flatpak search visualstudio` <br>
`flatpak install com.visualstudio.code` <br>
`flatpak run --command=sh com.visualstudio.code` <br>
`/app/bin/code --no-sandbox --no-zygote --disable-gpu-sandbox --disable-features=UsePortal` <br>

Use ls /app/bin to help find the app in these situations.

Brave browser example:
`flatpak search Brave` <br>
`flatpak install com.brave.Browser` <br>
`flatpak run --command=sh com.brave.Browser` <br>
`/app/brave/brave --no-sandbox --no-zygote --disable-gpu-sandbox --disable-features=UsePortal &` <br>

- Apps and their data are saved in ~/.local/share/flatpak and Aurora + Flatpak are stored in~/opt/.
- --user argument is built-in for this Flatpak since we have no root access.
- Some apps will not run the conventional way. Brave or Visual Studio are good examples.<br>

When running VS:
  
`flatpak run --command=sh com.visualstudio.code` <br>
`/app/bin/code --no-sandbox --no-zygote --disable-gpu-sandbox --disable-features=UsePortal` <br> <br>

When running Brave:

`flatpak run --command=sh com.brave.Browser` <br>
`/app/brave/brave --no-sandbox --no-zygote --disable-gpu-sandbox --disable-features=UsePortal &` <br> <br>

- To find where an app is after opening a shell for the app, run:
`ls /app/bin` <br> <br>


- 4k DPI scaling is easy to apply. Before starting an app run:

`aurora display 2` to set scaling to 2x. <br>
`aurora cursor 32` will set the cursor to 32px. <br>

 Customize to your liking. Applying changes requires restarting app. <br><br>

  #### Sharing files (Simalar to "Share with Linux")

 (optional) create a new folder under "MyFiles" (i.e. Steam_files)
 - Open Crosh (ctrl-alt-t) and type in: <br>
`vmc share borealis [folder path from MyFiles]`
- in my example this would be:  <br>
  `vmc share borealis Steam_files`
- if you simply want to share the whole downloads folder do: <br>
  `vmc share borealis Downloads`

 ### How it works:

- Borealis offers hardware acceleration support that makes Crostini's poor performance untenable. 
- Downloads Flatpak and its required dependencies from Arch's repository.
- Extracts Flatpak to ~/opt/flatpak and its dependencies to ~/opt/flatpak-deps
- Adds .bashrc for flatpak commands to actually work.


### Limitations:
- Currently lacking Crostini's integration with the shelf

- To do:
`Default web browser support, proper d-bus implementation, steam shortcuts`

### Changelog:
0.01: `Release` <br>
0.02: `Removed .bashrc file and added append capability. Added check to make sure not to install anywhere but Borealis.
Added uninstall and reinstall commands. Thanks to Saragon for the suggestions and teachimg me more about .bashrc.` <br>


### Acknowledgments
- Saragon making great suggestions, educating me about .bashrc, improving readme, finding bugs, and working on making Steam shortcuts a reality:
https://github.com/Saragon4005

- Thanks to DennisLfromGA for finding bugs, making great suggestions, and finding issues to running certain apps:
https://github.com/DennisLfromGA
  

