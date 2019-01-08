# TechArkit Youtube Channel Help Documents
 
Tech Arkit Youtube channel Provides you Information Technology related technical videos Like.


** Follow Us on Social Networking Sites **
* [Facebook](https://www.facebook.com/Linuxarkit/)
* [Email List](https://feedburner.google.com/fb/a/mailverify?uri=arkit)
* [Linkedin](https://in.linkedin.com/in/ravi-kumar-94530121)
* [Google Plus](https://plus.google.com/u/0/+RedhatEnterpriseLinuxStepbyStepGuide/posts)
* [Twitter](https://twitter.com/aravikumar48)
* [Youtube](https://www.youtube.com/Techarkit?sub_confirmation=1)
* [Email Address](aravikumar48@gmail.com)

- Linux Tutorial
- Certification Prep Guides
- AWS Video Tutorial
- Shell Scripting video tutorial
- So many other tutorial

Find the command line help here. We will update all the commands used in videos.

[DNS Server in Linux - Video](https://youtu.be/B6RprjoOdk4)
- [DNS Server Config File](https://github.com/techtutorials/TechArkit-YouTube/tree/master/DNS-Server)
```# yum install bind* -y ```
```# systemctl enable named-chroot.service```
```# systemctl start named-chroot.service```
```# systemctl enable named-chroot.service```
```# systemctl start named-chroot.service```

First edit [named.conf](https://github.com/techtutorials/TechArkit-YouTube/blob/master/DNS-Server/named.conf)
Next Edit [named.rfc1912.zones](https://github.com/techtutorials/TechArkit-YouTube/blob/master/DNS-Server/named.rfc1912.zones)
Forward Lookup Zone File [techarkit.local.for.zone](https://github.com/techtutorials/TechArkit-YouTube/blob/master/DNS-Server/techarkit.local.for.zone)
Reverse Lookup Zone File [techarkit.rev.zone](https://github.com/techtutorials/TechArkit-YouTube/blob/master/DNS-Server/techarkit.local.rev.zone)

Verify Named configuration using below command
```# /usr/sbin/named-checkconf -z /etc/named.conf```
```# named-checkzone server.techarkit.local techarkit.for.zone```
```# named-checkzone server.techarkit.local techarkit.rev.zone```



