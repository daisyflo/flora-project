Project 1
I have successfully deploy a LAMP Stack Website in AWS Cloud, And the steps i took while on this project is;
Step 1 — Installing Apache and Updating the Firewall
![image](https://user-images.githubusercontent.com/76633534/115258165-a68db280-a128-11eb-9c8a-f5a706ad616c.png)
![image](https://user-images.githubusercontent.com/76633534/115258305-c6bd7180-a128-11eb-823a-621a9f143140.png)
#run apache2 package installation
![image](https://user-images.githubusercontent.com/76633534/115258896-4e0ae500-a129-11eb-9d1c-5a3062eeab7c.png)
![image](https://user-images.githubusercontent.com/76633534/115259020-68dd5980-a129-11eb-8f7b-0be2eaf8205f.png)
To verify that apache2 is running as a Service in our OS, use following command
![image](https://user-images.githubusercontent.com/76633534/115259343-b5289980-a129-11eb-9788-e734338ed037.png)
First, let me try to check how i can access it locally in my Ubuntu shell, run:
![image](https://user-images.githubusercontent.com/76633534/115259814-1f413e80-a12a-11eb-9bf9-2e9b0a429dcc.png)
![image](https://user-images.githubusercontent.com/76633534/115259969-40099400-a12a-11eb-8780-3f0355a58941.png)
![image](https://user-images.githubusercontent.com/76633534/115260233-79da9a80-a12a-11eb-9c7a-27aaf3483c77.png)
![image](https://user-images.githubusercontent.com/76633534/115260473-b0181a00-a12a-11eb-9dda-eb5e53a7066b.png)
![image](https://user-images.githubusercontent.com/76633534/115260572-ca51f800-a12a-11eb-9790-fa519733f3ef.png)
![image](https://user-images.githubusercontent.com/76633534/115260635-db026e00-a12a-11eb-8d13-536ea2878fdf.png)
![image](https://user-images.githubusercontent.com/76633534/115260776-f5d4e280-a12a-11eb-9229-8f3100bb7e0e.png)
![image](https://user-images.githubusercontent.com/76633534/115260854-0a18df80-a12b-11eb-94d2-1017ff80f0ee.png)
![image](https://user-images.githubusercontent.com/76633534/115260972-21f06380-a12b-11eb-80e1-d107f330fbc4.png)
![image](https://user-images.githubusercontent.com/76633534/115261069-392f5100-a12b-11eb-9416-6a0680edae57.png)
![image](https://user-images.githubusercontent.com/76633534/115261178-4cdab780-a12b-11eb-9590-3597fccfe254.png)
![image](https://user-images.githubusercontent.com/76633534/115261297-67149580-a12b-11eb-831e-6f725e2bb1b7.png)
![image](https://user-images.githubusercontent.com/76633534/115261422-814e7380-a12b-11eb-997c-73a5dfc13977.png)
i have totest how my Apache HTTP server can respond to requests from the Internet. Open a web browser of my choice and try to access following url
http://<Public-IP-Address>:80
![image](https://user-images.githubusercontent.com/76633534/115262226-3c770c80-a12c-11eb-8125-9d481107fde9.png)
Step 2 — Installing MySQL
![image](https://user-images.githubusercontent.com/76633534/115262690-adb6bf80-a12c-11eb-8749-8741f0a7f31e.png)
![image](https://user-images.githubusercontent.com/76633534/115262847-cde67e80-a12c-11eb-816f-dd6c1701bc78.png)
![image](https://user-images.githubusercontent.com/76633534/115262962-ec4c7a00-a12c-11eb-9d5a-76bf8a6d54a6.png)
 it’s recommended that i run a security script that comes pre-installed with MySQL. This script will remove some insecure default settings and lock down access to my database system. Start the interactive script by running:
![image](https://user-images.githubusercontent.com/76633534/115263901-b8258900-a12d-11eb-8d76-eab5304e84f0.png)
![image](https://user-images.githubusercontent.com/76633534/115263619-7a286500-a12d-11eb-9f54-b17a86b2b21a.png)
![image](https://user-images.githubusercontent.com/76633534/115264018-d68b8480-a12d-11eb-9004-3693d8d74350.png)
  test if I'm able to log in to the MySQL console by typing
![image](https://user-images.githubusercontent.com/76633534/115264268-0e92c780-a12e-11eb-8abb-e3bde181e072.png)
![image](https://user-images.githubusercontent.com/76633534/115264839-924cb400-a12e-11eb-8046-a35303a38ea2.png)
Step 3 — Installing PHP. To install these 3 packages at once, run:
![image](https://user-images.githubusercontent.com/76633534/115265520-36cef600-a12f-11eb-83e3-19204e5e67b1.png)
 ![image](https://user-images.githubusercontent.com/76633534/115265631-536b2e00-a12f-11eb-8ded-ae860e4bc27a.png)
![image](https://user-images.githubusercontent.com/76633534/115265735-6aaa1b80-a12f-11eb-85b7-9f492f7035ac.png)
Once the installation is finished, i can run the following command to confirm your PHP version:
 ![image](https://user-images.githubusercontent.com/76633534/115265980-ac3ac680-a12f-11eb-93af-34d8520967d0.png)
 Step 4 — Creating a Virtual Host for your Website using Apache
 Create the directory for projectlamp using ‘mkdir’ command as follows:
 ![image](https://user-images.githubusercontent.com/76633534/115266571-3be07500-a130-11eb-9ac5-ce203023723d.png)
Next, assign ownership of the directory with the $USER environment variable, which will reference my current system user: 
 ![image](https://user-images.githubusercontent.com/76633534/115266978-9548a400-a130-11eb-8f25-6e466fd35d7e.png)
  Then, create and open a new configuration file in Apache’s sites-available directory using your preferred command-line editor. Here, we’ll be using vi or vim (They are the same by the way):
sudo vi /etc/apache2/sites-available/projectlamp.conf 
  ![image](https://user-images.githubusercontent.com/76633534/115267985-b3fb6a80-a131-11eb-98ac-3dbf6b3941e9.png)
use a2ensite command to enable the new virtual host:
  ![image](https://user-images.githubusercontent.com/76633534/115268306-0c326c80-a132-11eb-8dde-54c0d9609c09.png)
To disable Apache’s default website use a2dissite command , type:
  ![image](https://user-images.githubusercontent.com/76633534/115268556-4bf95400-a132-11eb-8100-e5491cda3f4f.png)
  To make sure my configuration file doesn’t contain syntax errors, run:
![image](https://user-images.githubusercontent.com/76633534/115268777-895de180-a132-11eb-8941-fa5f86c75cc6.png)
Finally, reload Apache so these changes take effect:
  ![image](https://user-images.githubusercontent.com/76633534/115268932-b3af9f00-a132-11eb-9586-bf0f25fcc620.png)
My new website is now active, but the web root /var/www/projectlamp is still empty. Create an index.html file in that location so that i can test that the virtual host works as expected:
  ![image](https://user-images.githubusercontent.com/76633534/115269217-ff624880-a132-11eb-9600-8fb9bde068f5.png)
Now go to your browser and try to open your website URL using IP address:
http://<Public-IP-Address>:80
  ![image](https://user-images.githubusercontent.com/76633534/115269453-3cc6d600-a133-11eb-9df5-78632d97d649.png)
Step 5 — Enable PHP on the website
  In case i want to change this behavior, you’ll need to edit the /etc/apache2/mods-enabled/dir.conf file and change the order in which the index.php file is listed within the DirectoryIndex directive:
  sudo vim /etc/apache2/mods-enabled/dir.conf
  ![image](https://user-images.githubusercontent.com/76633534/115269867-a3e48a80-a133-11eb-91eb-7f385d5fdc98.png)
  After saving and closing the file, i will need to reload Apache so the changes take effect:
  ![image](https://user-images.githubusercontent.com/76633534/115274201-561e5100-a138-11eb-8068-22e8f4346255.png)
Create a new file named index.php inside your custom web root folder:
  $ vim /var/www/projectlamp/index.php
  ![image](https://user-images.githubusercontent.com/76633534/115274679-da70d400-a138-11eb-85ee-dc931f501084.png)
![image](https://user-images.githubusercontent.com/76633534/115274950-1b68e880-a139-11eb-831e-8bcd69f25cc2.png)
After checking the relevant information about my PHP server through that page, it’s best to remove the file you created as it contains sensitive information about your PHP environment -and  Ubuntu server.
![image](https://user-images.githubusercontent.com/76633534/115275076-3c313e00-a139-11eb-95f2-d9200e0f1b30.png)

