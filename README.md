# WMI-Detection
Monitoring Windows Management Instrumentation ETLs (Event Trace Logs) and activities using Powershell and Splunk's SIEM


<h2>Environments and Tools Used</h2>

- WMI (Windows Management Instrumentation)
- Powershell
- Splunk Enterprise SIEM 


<h2>Operating Systems Used </h2>

- Windows 2019


 <h2>Configuration Steps</h2>

<p>
<img src="https://github.com/ChadH2O/WMI-Tracing/assets/146133122/6b4dabf0-4794-41cb-86a8-74af28a0f1b5" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open the search & reporting app in Splunk Enterprise SIEM
</p>
<br />

<p>
<img src="https://github.com/ChadH2O/WMI-Tracing/assets/146133122/33a3005d-0ba9-4c4b-85fa-ee5be4e65d5e" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Then click on Data Summary towards the bottom of the page
</p>
<br />

<p>
<img src="https://github.com/ChadH2O/WMI-Tracing/assets/146133122/dcefd78f-ec2a-42b6-8ba5-ef276384e960" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This gives you a compact summary of hosts forwarding logs to your Splunk server, configured log sources on these hosts, and source types. Next click the 'Sources' tab.
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/WMI-Tracing/assets/146133122/d5f0478e-ed4c-4862-8d78-1ffaf2139259" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on the WMI Trace source to view the WMI trace logs
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/WMI-Tracing/assets/146133122/6d6c29c2-57c8-488e-b1cb-f50ade340ddd" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
At the top of the page you will see the Splunk query used to view the ETL's in the search bar (source="Splunk-ETW://WMITrace"), to narrow down your search and find the correct product query log use keywords associated with the product query. Since you queried the Win32_Product WMI class , you should look for recent events that have product mentioned in it. 
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/WMI-Tracing/assets/146133122/70cea5ee-902e-442a-a1bd-27c9735a48b7" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
As you can see the correct product query log was located using the keyword narrowing method in the search bar. Also known as "source filtering".
</p>
<br />
 

<p>
<img src="https://github.com/ChadH2O/WMI-Tracing/assets/146133122/e4e1c431-b170-4185-95af-879f85805f94" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, run a WMI query in Powershell. This query creates a list of all the installed applications along with the versions in the local host. 
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/WMI-Tracing/assets/146133122/e084dffb-ae13-4f81-9345-4f8a92558b8f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
After running the query successfully you should be able to view a list of the installed applictions.
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/WMI-Tracing/assets/146133122/ea799c03-405b-42f2-a657-9f041dbb2082" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
Create a remote user by using the following command: wmic /user:COMMENSURATE\emmanueltoller /password:t0tallySecre7? /node:"windows10" process call create "net user sus ImAP@55w*rd /Add". The purpose of doing this is to simulate malicious behavior. 
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/WMI-Tracing/assets/146133122/19426ade-47e3-4307-a1ed-b127dac462b1" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
WMI will then provide a list of user accounts for DC1
</p>
<br />


<p>
<img src="https://github.com/ChadH2O/WMI-Tracing/assets/146133122/ea799c03-405b-42f2-a657-9f041dbb2082" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
Now you can investigate the generated results in Splunk
</p>
<br />



