# EENG-406---VLSI
VLSI - Spring 2024

# EE406
### Required EDA software
1. Open the PowerShell and install WSL<br>
`wsl --install -d Ubuntu-22.04`<br>
You will be prompted to create a UNIX username and password.<br>
This UNIX username and password have no relationship to your Windows username and password.<br>
To avoid any confusion use a different username
2. [Install Docker Desktop](https://docs.docker.com/desktop/install/windows-install/)<br>
3. Start Ubuntu (either by typing `wsl` into the Windows's PowerShell or selecting the Ubuntu app in the Window's Start Menu) <br>
Your unix user's home directory is:<br>
`/home/<unix username>`<br>
Your Windows user's home directory is:<br>
`/mnt/c/Users/<windows username>`
5. clone the [iic-osic-tools](https://github.com/iic-jku/IIC-OSIC-TOOLS) container onto your computer (for example into your Windows user's folder)<br>
`git clone --depth=1 https://github.com/iic-jku/iic-osic-tools.git`<br>
*Example*<br>
Windows user's folder: `C:\Users\claudio`<br>
In Unix, the Windows user's folder is accessible as:
`/mnt/c/Users/claudio`<br>
5. Start Docker Desktop
6. Browse to the iic-osic-tools directory<br>
`cd /mnt/c/Users/claudio/iic-osic-tools`<be>
7. Start the container using the script `./start_x.sh`<br>
**NOTE:** in the script, all user data is persistently mounted in the directory pointed to by the environment variable `DESIGNS` <br>
The default is `$HOME/eda/designs`<br>
To change where the user data is mounted edit the `./start_x.sh` script and modify the definition of the variable `DESIGNS`<br>
*Example*<br>
`DESIGNS="/mnt/g/My Drive/eda/designs"`
8. If there is a warning asking about Xauthority not found, run the following command.
`touch ~/.Xauthority`
9. If there is a warning and the terminal asks you to 
10. If everything goes as it should, you will see a terminal with the prompt `/foss/designs >`. <br>
This is your working directory where all your design data goes.
11. The default PDK is the `sky130A`. However, the container supports also other PDKs.<br>
The available PDKs are:<br>
`gf180mcuC`<br>
`sg13g2`<br>
`sky130A`<br>
If you want to switch to the IHP PDK type:<br>
`iic-pdk sg13g2`<br>
To skip typing this command every time, create a `.designinit` text file in your design directory with the following lines:
   ```
   PDK_ROOT=/foss/pdks
   PDK=sg13g2
   PDKPATH=/foss/pdks/sg13g2
   ```
12. If the terminal screen is glitching out, download MobaXterm Home Edition. <br>
[download link](https://mobaxterm.mobatek.net/download-home-edition.html) <br>
Run the installation software without any changes. Then restart your computer and rerun starting from step 5. This should resolve the screen issue.
13. Install Python package PyLTSpice version 3.1 by running the command <br>
`pip install PyLTSpice==3.1`<br>

### MatLab
1. Go to [MathWorks downloads](https://www.mathworks.com/downloads/).
2. Install the latest version for the correct operating system.
3. Login with a MathWorks Account.
4. Accept terms and agreements
5. Log in with MathWorks account.
6. Select Individual license.
7. Leave default settings and click next until you reach install.

### Hspice/Ngspice Toolbox for Matlab ([link](https://www.cppsim.com/download_hspice_tools.html)) <br>
1. Go to ([link](https://www.cppsim.com/download_hspice_tools.html)).
2. Scroll down to the section titled "Hspice Toolbox for Matlab and Octave (also for use with Ngspice)"
3. Click the "TAR.GZ" button to select "Download Hspice Toolbox for Matlab and Octave (hspice_toolbox.tar.gz)".
4. Open Windows Powershell and navigate to the home directory by typing the following command
<br> `cd ~` <br>
5. Create a new directory to place the toolbox in by typing the following command
<br> `mkdir Matlab_Toolboxes` <br>
6. Navigate to the downloads folder by entering
<br> `cd Downloads` <br>
7. Enter the following command to untar the downloaded folder into the new directory
<br> `tar -xzvf hspice_toolbox.tar.gz -C '..\Matlab_Toolboxes'` <br>
8. Open Matlab
9. HOME -> ENVIRONMENT -> Add-Ons -> Get Add-Ons
10. Search for add-ons: MinGW
11. Select "MATLAB Support for MinGW-w64 C/C++/Fortran Compiler"
12. Install -> Install -> Agree -> Next -> Wait for download to complete -> Close
13. Exit the Add-On Explorer.
14. Under the "Command Window" navigate to the following directory with your username
<br> `C:\Users\camer\Matlab_Toolboxes\HspiceToolbox` <br>
15. Enter the following command
<br> `mex loadsig.c` <br>

### Anaconda 
1. Go to the following website link: ([link](https://docs.anaconda.com/free/anaconda/install/index.html))
2. Click on the green button that reads "Anaconda install for Windows".
3. Launch the installer after it has downloaded and follow its instructions.
