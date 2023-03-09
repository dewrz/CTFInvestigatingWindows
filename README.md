# CTFInvestigatingWindows

The goal of this machine is to investigate a Windows system that has been recently compromised. There are 16 questions that we will be answering along the way, so let's dive in. 

1. What's the version and year of the windows machine? Answer: Windows Server 2016<br>
<i>*This question can be frustrating if you were trying to enumerate the actual system version number.</i>
<br>
<br>
<a href="https://imgur.com/aTgUwbe"><img src="https://i.imgur.com/aTgUwbe.jpg" title="source: imgur.com" /></a>
<br>
<br>
By running the next command, I was able to answer the next two questions. 

2. Which user logged in last? Answer: Administrator 

3. When did John log onto the system last? Answer: 3/2/2019 5:48:32 PM
<br>
<a href="https://imgur.com/OBhkSvY"><img src="https://i.imgur.com/OBhkSvY.jpg" title="source: imgur.com" /></a>
<br>
<br>
This next question was surprisingly a rough one. I spent a great deal of time trying to figure out different ways to answer this question. In short, there was no easy answer. I did find it explained that you should open regedit and navigate to HKEY_LOCAL_MACHINE > SOFTWARE > Microsoft > Windows > CurrentVersion > Run. There you will find a file called UpdateSvc that is executing p.exe. When I Googled “p.exe” it came back as a malicious file and when searching “C:\tmp” there was a host of suspicious looking files. * Credit to Seemz 
<br>
4. What IP does the system connect to when it first starts? Answer: 10.34.2.3 
<br>
<br>
<a href="https://imgur.com/6BfoKCT"><img src="https://i.imgur.com/6BfoKCT.jpg" title="source: imgur.com" /></a>
<br>
<br>
5. What two accounts had administrative privileges (other than the Administrator user)? Answer: Guest & Jenny
<br>
<br>
<a href="https://imgur.com/s56jvHB"><img src="https://i.imgur.com/s56jvHB.jpg" title="source: imgur.com" /></a>
<br>
<br>





