I have built a flexible foundation for serving PHP websites and applications to my visitors, using Nginx as web server and MySQL as database management system.
Steps i took to implement this project is:
Step 1 – Installing the Nginx Web Server
apt install to get Nginx installed:
![image](https://user-images.githubusercontent.com/76633534/115281600-1a3bb980-a141-11eb-9ee6-7525ace80b8f.png)
![image](https://user-images.githubusercontent.com/76633534/115281723-37708800-a141-11eb-94ab-f311d825d676.png)
![image](https://user-images.githubusercontent.com/76633534/115281781-48b99480-a141-11eb-8885-50d1714f234e.png)
![image](https://user-images.githubusercontent.com/76633534/115282261-ec0aa980-a141-11eb-8a83-3184ab1912cd.png)
![image](https://user-images.githubusercontent.com/76633534/115282319-02186a00-a142-11eb-9064-9dbd55d676a3.png)
To verify that nginx was successfully installed and is running as a service in Ubuntu, run:
![image](https://user-images.githubusercontent.com/76633534/115282607-4c99e680-a142-11eb-8240-d40020480b56.png)
First, let me try to check how i can access it locally in our Ubuntu shell, run:
![image](https://user-images.githubusercontent.com/76633534/115282881-a1d5f800-a142-11eb-8da2-6f4e971eeb9d.png)
Open a web browser of your choice and try to access following url
http://<Public-IP-Address>🈵
  ![image](https://user-images.githubusercontent.com/76633534/115283240-01340800-a143-11eb-9345-a5c1e5d4ff14.png)
Step 2 — Installing MySQL
Again, use apt to acquire and install this software:
  ![image](https://user-images.githubusercontent.com/76633534/115283642-8ddec600-a143-11eb-98bf-38a4fea5a073.png)
![image](https://user-images.githubusercontent.com/76633534/115283715-a3ec8680-a143-11eb-81ad-a11744f1540b.png)
![image](https://user-images.githubusercontent.com/76633534/115283766-b49cfc80-a143-11eb-8215-76548dcefb41.png)
 This script will remove some insecure default settings and lock down access to my database system
  ![image](https://user-images.githubusercontent.com/76633534/115284218-4e64a980-a144-11eb-8b1a-ef057b424363.png)
![image](https://user-images.githubusercontent.com/76633534/115284292-65a39700-a144-11eb-9c5d-9ad57c231f4d.png)
![image](https://user-images.githubusercontent.com/76633534/115284354-7e13b180-a144-11eb-917c-35582b78232c.png)
When i finished,i test if i was able to log in to the MySQL console by typing:
  ![image](https://user-images.githubusercontent.com/76633534/115284650-d945a400-a144-11eb-9053-6aa0f4e5cc58.png)
Step 3 – Installing PHP
  To install these 2 packages at once, run:
  ![image](https://user-images.githubusercontent.com/76633534/115286403-ef546400-a146-11eb-8714-e415f6acd9f4.png)
![image](https://user-images.githubusercontent.com/76633534/115286486-072be800-a147-11eb-9c41-7934fc88fb73.png)
Step 4 — Configuring Nginx to Use PHP Processor
  Create the root web directory for my_domain as follows:
  ![image](https://user-images.githubusercontent.com/76633534/115286772-5d009000-a147-11eb-9100-2befe190f6d9.png)
  Next, assign ownership of the directory with the $USER environment variable, which will reference your current system user:
  ![image](https://user-images.githubusercontent.com/76633534/115286912-8f11f200-a147-11eb-95de-e59d73541e90.png)
  Then, open a new configuration file in Nginx’s sites-available directory using my preferred command-line editor. Here, i use nano:
$ sudo nano /etc/nginx/sites-available/projectLEMP
  This will create a new blank file. Paste in the following bare-bones configuration
  ![image](https://user-images.githubusercontent.com/76633534/115287340-119ab180-a148-11eb-9af4-f95bc8f7ceca.png)
Activate my configuration by linking to the config file from Nginx’s sites-enabled directory:
  ![image](https://user-images.githubusercontent.com/76633534/115287586-5d4d5b00-a148-11eb-9b2b-6434d2c412b9.png)
 test your configuration for syntax errors by typing:
  ![image](https://user-images.githubusercontent.com/76633534/115287952-c3d27900-a148-11eb-91f2-2077e244feaf.png)
also need to disable default Nginx host that is currently configured to listen on port 80, for this run:
  ![image](https://user-images.githubusercontent.com/76633534/115288146-009e7000-a149-11eb-818c-62650c5882d2.png)
reload Nginx to apply the changes:
  ![image](https://user-images.githubusercontent.com/76633534/115288333-3c393a00-a149-11eb-9eca-9bd32c73d9c6.png)
 Create an index.html file in that location so that we can test that your new server block works as expected:
  ![image](https://user-images.githubusercontent.com/76633534/115288594-828e9900-a149-11eb-82bb-9255c13c1f5f.png)
Now go to your browser and try to open your website URL using IP address:
![image](https://user-images.githubusercontent.com/76633534/115288822-cf726f80-a149-11eb-9fcc-5fd9d158ba6a.png)
http://<Public-IP-Address>:80
  Step 5 – Testing PHP with Nginx
   Open a new file called info.php within your document root in your text editor:
  nano /var/www/projectLEMP/info.php
  ![image](https://user-images.githubusercontent.com/76633534/115289267-4c054e00-a14a-11eb-82bd-6b56c19642ad.png)
  You can now access this page in your web browser by visiting the domain name or public IP address you’ve set up in your Nginx configuration file, followed by /info.php:
http://`server_domain_or_IP`/info.php
  ![image](https://user-images.githubusercontent.com/76633534/115290092-2593e280-a14b-11eb-96ae-07160aebc82f.png)
  to remove that file
  Step 6 — Retrieving data from MySQL database with PHP
  ![image](https://user-images.githubusercontent.com/76633534/115290716-c8e4f780-a14b-11eb-9362-f892a95ec1c0.png)
You can test if the new user has the proper permissions by logging in to the MySQL console again, this time using the custom user credentials:
  ![image](https://user-images.githubusercontent.com/76633534/115291572-d3ec5780-a14c-11eb-8677-4592f68a0b39.png)
![image](https://user-images.githubusercontent.com/76633534/115291661-ee263580-a14c-11eb-8413-605f1385c937.png)
Now you can create a PHP script that will connect to MySQL and query for your content. Create a new PHP file in your custom web root directory using your preferred editor.       nano /var/www/projectLEMP/todo_list.php
![image](https://user-images.githubusercontent.com/76633534/115292415-d4d1b900-a14d-11eb-8cc8-22f3ddb2661c.png)
![image](https://user-images.githubusercontent.com/76633534/115292625-22e6bc80-a14e-11eb-9c71-88f447abecfa.png)
![image](https://user-images.githubusercontent.com/76633534/115292231-9d630c80-a14d-11eb-97d8-1e2e2c66575e.png)
  ![image](https://user-images.githubusercontent.com/76633534/115293661-81606a80-a14f-11eb-8f46-a5cda0d1336e.png)



  
