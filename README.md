# CTFInvestigatingWindows

The goal of this machine is to investigate a Windows system that has been recently compromised. There are 16 questions that we will be answering along the way, so let's dive in. 

1. What's the version and year of the windows machine? Answer: Windows Server 2016<br>
<i>*This question can be frustrating if you were trying to enumerate the actual system version number.</i>
<br>
<br>
<img src="https://i.imgur.com/aTgUwbe.jpg" title="source: imgur.com" />
<br>
<br>
By running the next command, I was able to answer the next two questions. 

2. Which user logged in last? Answer: Administrator 

3. When did John log onto the system last? Answer: 3/2/2019 5:48:32 PM
<br>
<img src="https://i.imgur.com/OBhkSvY.jpg" title="source: imgur.com" />
<br>
<br>
This next question was surprisingly a rough one. I spent a great deal of time trying to figure out different ways to answer this question. In short, there was no easy answer. I did find it explained that you should open regedit and navigate to HKEY_LOCAL_MACHINE > SOFTWARE > Microsoft > Windows > CurrentVersion > Run. There you will find a file called UpdateSvc that is executing p.exe. When I Googled “p.exe” it came back as a malicious file and when searching “C:\tmp” there was a host of suspicious looking files. * Credit to Seemz 
<br>
<br>
4. What IP does the system connect to when it first starts? Answer: 10.34.2.3 
<br>
<br>
<img src="https://i.imgur.com/6BfoKCT.jpg" title="source: imgur.com" />
<br>
<br>
5. What two accounts had administrative privileges (other than the Administrator user)? Answer: Guest & Jenny
<br>
<br>
<img src="https://i.imgur.com/s56jvHB.jpg" title="source: imgur.com" />
<br>
<br>
The next 3 questions were answered by pulling up the Task Scheduler.
<br>
<br>
6. What's the name of the scheduled task that is malicious? Answer: Clean File System 
<br>
7. What file was the task trying to run daily? Answer: nc.ps1 
<br>
8. What port did this file listen locally for? Answer: 1348 
<br>
<br>
<img src="https://i.imgur.com/bLClGme.jpg" title="source: imgur.com" />
<br>
<br>
9. When did Jenny last logon? Answer: Never 
<br>
<br>
<img src="https://i.imgur.com/R4Cnvfk.jpg" title="source: imgur.com" />
<br>
<br>
10. At what date did the compromise take place? Answer: 03/02/2019 
<br>
<br>
<img src="https://i.imgur.com/vNK9aqS.jpg" title="source: imgur.com" />
<br>
<br>
This next question was a bit confusing, due to it being poorly worded, so I used the “hint” and filtered the event ID 4672 by date/time. 
<br>
<br>
11. At what time did Windows first assign special privileges to a new logon? Answer: 03/02/2019 04:04:49 PM 
<br>
<br>
<img src="https://i.imgur.com/ajzK6X7.jpg" title="source: imgur.com" />
<br>
<br>
For the next question, I actually came across the answer when looking through the suspicious files in the c:\tmp\ folder. 
<br>
<br>
12. What tool was used to get Windows passwords? Answer: Mimikatz 
<br>
<br>
<img src="https://i.imgur.com/SX82mPr.jpg" title="source: imgur.com" />
<br>
<br>
The next question, we looked at the win hosts file. We see two entries for Google with IP addresses that aren’t 8.8.8.8 or 8.8.4.4. 
<br>
<br>
13. What was the attacker's external control and command servers IP? Answer: 76.32.97.132 
<br>
<br>
<img src="https://i.imgur.com/eis8NCn.jpg" title="source: imgur.com" />
<br>
<br>
With this being a Windows machine, we can assume that it is using Microsoft Internet Information Services  (IIS) which uses the default folder inetpub. 
<br>
<br>
14. What was the extension name of the shell uploaded via the servers website? Answer: .jsp 
<br>
<br>
<img src="https://i.imgur.com/jv9J7X4.jpg" title="source: imgur.com" />
<br>
<br>
For this next question we looked up the Windows firewall log in event viewer for outside connections. 
<br>
<br>
15. What was the last port the attacker opened? Answer: 1337 
<br>
<br>
<img src="https://i.imgur.com/JYDsk8m.jpg" title="source: imgur.com" />
<br>
<br>
As we saw earlier while viewing the hosts file, we can see that DNS poisoning had taken place. 
<br>
<br>
16. Check for DNS poisoning, what site was targeted? Answer: google.com 
<br>
<br>
<img src="https://i.imgur.com/eis8NCn.jpg" title="source: imgur.com" />






































