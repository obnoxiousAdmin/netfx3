# netfx3
Files needed for the offline installation of netfx3 when using dism.exe/Enable-WindowsOptionalFeature.

🛈 Note: This was only tested on 24H2. YMMV

Since the 24H2 ISO didn't include `DesktopDeployment.cab` in the `.\sources\sxs\` directory, you will get errors in CBS.log and dism.log such as:
* 0x80070003 - ERROR_PATH_NOT_FOUND
* 0x800f081f - CBS_E_SOURCE_MISSING

Simply add `DesktopDeployment.cab` along side of `Microsoft-Windows-NetFx3-OnDemand-Package~31bf3856ad364e35~amd64~~.cab` in your `sxs` sources directory when using the `Sources` and `LimitAccess` flags.

I was able to acquire `DesktopDeployment.cab` by using a VM to download and install netfx3 using WU as the source. You can find the file `DesktopDeployment.cab` in `C:\WINDOWS\CbsTemp\01234567_0123456789\FodWU\` (note that the GUID changes).

Legal Disclaimer: I do not own the cab files found in this archive. I simply downloaded the cab files from WU and re-uploaded them here for easy sharing. Microsoft owns the cab files.
