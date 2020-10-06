# isolated
Isolated sound card - 192khz, 24 bit, implementing the AI-AIS-v1.0

[If you want to discuss these products, or topics around hearing, acoustics and audio, join the audio injector email list.](https://lists.audioinjector.net/mailman/listinfo/people)

# Auto Setup

Coming soon !

# Manual Setup

Make sure you have a recent enough firmware Kernel version 5.4.58 or later (4.19.xx later then 17th July) which includes the Isolated machine driver updates :

```
sudo rpi-update
```

Edit your /boot/config.txt file to disable dtparam=audio (the # below comments it out):
```
#dtparam=audio
```

Edit your /boot/config.txt file to enable the Ultra's device tree overlay :
```
dtoverlay=audioinjector-isolated-soundcard
```  

# Manual Setup bash command script :
```
sudo rpi-update
# firstly disable PWM audio
sed -i \"s/^\s*dtparam=audio/#dtparam=audio/\" /boot/config.txt
# now check to see the correct device tree overlay is loaded ...
cnt=`grep -c audioinjector-isolated-soundcard /boot/config.txt`
if [ "$cnt" -eq "0" ]; then
  echo '# enable the AudioInjector.net sound card
  dtoverlay=audioinjector-isolated-soundcard' >> /boot/config.txt
fi
```
# case

Michael Gardner's 3D printable case : https://www.myminifactory.com/object/3d-print-136656

# Hardware Assembly
 -- to come --

Check out our other products :

http://audioinjector.net

https://shop.audioinjector.net
