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
