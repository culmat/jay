# Jay


Jay is a java application skeleton for building a tray traffic light like signalization.


When starting jay reads *.cfg files in your <homedir>/.jay folder. Each config file represents a traffic light bulb. The files are java property files (key/value pair). 

```
name=Jay
class=jay.monitor.sensor.DummySensor
```

This bulb would have the label Jay and the class DummySensor would implement the sensor logic. Each sensor runs in it's own deamon thread.

Use jay to build your own monitoring of whatever you want.

# Some Screenshots

![Traffic light](images/jaylights.PNG)

![Jay message](images/jaytray.PNG)

# Installation on Windows
## Download the binary. 
You can look up the current jay version at https://jitpack.io/com/github/baloise/jay/-SNAPSHOT/maven-metadata.xml
```
powershell -Command "$proxy = [System.Net.WebRequest]::GetSystemWebProxy();$proxy.Credentials = [System.Net.CredentialCache]::DefaultCredentials;$wc = new-object system.net.WebClient;$wc.proxy = $proxy;$wc.DownloadFile('https://raw.githubusercontent.com/baloise/jay/master/install.bat', 'install_jay.bat');"
install_jay.bat
del install_jay.bat

```

## Create start up item
```
echo powershell -Command Start-Process 'javaw.exe' '-cp "%userprofile%\jay.jar" jay.monitor.Main' -NoNewWindow > "%APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup\jay.bat"
```

## Run
```
powershell -Command Start-Process 'javaw.exe' '-cp "%userprofile%\jay.jar" jay.monitor.Main' -NoNewWindow
```
