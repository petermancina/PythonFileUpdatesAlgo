<h1>Algorithm for File Updates in Python</h1>

<h2>Project Description</h2>
This project simulates how a security professional at a company regularly updates a file that identifies the employees who can access restricted company content, in particular, private customer records. Employees are restricted based on their IP address, and this is enforced through an IP allow list for a restricted subnet. This security professional writes a python algorithm-bearing function that uses an access list txt file and a list of IP addresses to remove from the access list. The function runs an algorithm to check if the allow list contains any IP addresses on the remove list. It then automates the removal of any IP addresses on the remove list from the access list.

<h2>Assign your file object names</h2>
Here we will assign "import_file" for our allow_list.txt that includes the IP addresses of employees who can view protected or restricted client records. We will assign "remove_list" for a list of IPs of employees that can no longer view protected/restricted records and that we want to remove from the access list.
<p align="center">
<br/>
<img src="https://i.imgur.com/UH77AJr.png" height="100%" width="100%" alt="Assign your file object names"/>
</p>
<h2>Define your function </h2>
Next we define our function "update_file" using <b>def</b> and tell the function to use "import_file" and "remove_list" as arguments by putting them in parentheses, separated by a comma.
<p align="center">
<br/>
<img src="https://i.imgur.com/kj5JT4Y.png" height="100%" width="100%" alt="Define your function"/>
</p>
<h2>Read the file contents</h2>
We then tell the function to open and read the access list file (import_file) and store the contents in ip_addresses. We do this by creating a <b>with</b> statement using <b>open()</b>, "r" for read and the .read() method.
<p align="center">
<br/>
<img src="https://i.imgur.com/KPz4xre.png" height="100%" width="100%" alt="Read the file contents"/>
</p>
<h2>Convert the string into a list</h2>
We then use .split() method to turn the string of allow list IP addresses into a list IPs that the algorithm will loop through individually one-by-one to check and potentially remove.
<p align="center">
<br/>
<img src="https://i.imgur.com/DxWK5QW.png" height="100%" width="100%" alt="Convert the string into a list"/>
</p>
<h2>Iterate through the remove list and remove IP addresses from the allow list</h2>
We then write a <b>for</b> loop to tell the function to loop through the remove_list and to use the name "element" for the variable representing remove_list IPs. We use an <b>if</b> statement tell the algorithm that if it finds any of the remove_list IPs (element) in ip_addresses (our access list split by IP address), to remove them using the .remove() method. 
<p align="center">
<br/>
<img src="https://i.imgur.com/hkUqcSZ.png" height="100%" width="100%" alt="Iterate through the remove list and remove IP addresses from the allow list"/>
</p>
<h2>Update the file with the revised list of IP addresses</h2>
We then tell the function to convert the updated allow list in ip_addresses from a list format back into a string format so that it will be able to write it back to the original txt file. We do this by using the .join() method. We then tell the function to re-open the original file (import_file) using "w" for write since we will overwrite what is currently in the original access_list.txt file stored in import_file. We tell the function to consider import_file as "file" while opened. We then use the .write() method to write the updated access list to import_file (file) by including it as an argument of .write().
<p align="center">
<br/>
<img src="https://i.imgur.com/cPp4IFj.png" height="100%" width="100%" alt="Update the file with the revised list of IP addresses"/>
</p>
<h2>Call your function and check that it worked</h2>
With the update_file function fully coded, we can call it and pass to it our specific allow_list.txt file and our list of IPs that we would like to remove from the allow_list.txt file. We can view the updated allow_list.txt with the IPs removed by using a <b>with</b> statement, open(), and with "r" for read. We store the contents in the variable "text" and print text to screen to view the contents.
<p align="center">
<br/>
<img src="https://i.imgur.com/7Cmcmd3.png" height="100%" width="100%" alt="Call your function and check that it worked"/>
</p>
<h2>Summary</h2>
This simple algorithm allows security professionals to update txt files quickly to make modifications to access lists. This algorithm can be used for other use cases as well: to remove revoked users from an authorization list, update firewall allowlists or denylists, remove decommissioned servers from monitoring targets, cleaning old device IDs from an inventory file, removing inactive email addresses from notification lists, filtering banned domains, URLs, usernames, or API clients, maintaining software license or subscription lists, or synchronizing a local list with a separate revocation list. It is worth noting that if a particular IP address is included multiple times in an access list, this function may miss additional entries of that IP address. It is also best practice to make a backup copy of your access list prior to using this function to roll-back the list in the case that an error occurs during processing or in the case that you have incorrectly written your algorithm. 


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>

