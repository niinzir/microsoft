## Using Windows Update

_Windows Update_ is a utility that conencts to the Microsoft website and check o
ensure that you ahve the most up to date versions of Microsoft products. Some of
the common update categories associated with Windows Update are as follows:

+ Citrical updates
+ Service packs
+ Drivers

There are two ways user receive updates: directly from Microsoft or using
Microsoft Windows SErver Update SErver (WSUS). WSUS runs on a Windows server,
and that server goes out to the Microsoft website and downloads the updates for
your Windows clients.

Windows Update has a few command-line options that can be used to help configure
and maintain it.

To start Windows Update from a command prompt, you can type _wuapp.exe_

Another command-line option that works with Windows Update is called Windows
Update Automatic Client (_wuauclt.exe_), which offers the following options:

__Detectnow:__ When working with WSUS, waiting for detection to start can become
very time-consuming. To run the _detectnow_ option, type the following command
at the command prmopt: `wuauclt.exe /detectnow`

__Reportnow__ This command allows you to send all queued reporting events to the
server asynchronously. To execute this command, type `wuauclt.exe /reportnow`
at the command prompt.

__Resetauthoriztion__ WSUS uses a cookie on Windows 10 client computers to store
different types of information. By default, an hour after the cookie is created,
it expires. If you need the cookie to expire now, you can use the
_resetauthorization_ option along with the _detectnow_ option. Using these
options will expire the cookie, initiate detection, and have WSUS update
computer group membership. To execute this command, type `wuauclt.exe
/resetauthorization /detectnow` at the command prompt.
