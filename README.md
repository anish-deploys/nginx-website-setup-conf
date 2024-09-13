# Creating and Setting up virtual host for the website by Nginx 

<h2>1. Installing Nginx </h2>

~sudo apt update 

~sudo apt install nginx

Type "localhost" in your browser


  ![image](https://github.com/user-attachments/assets/271f46a5-92d3-4bd9-baaf-bd3692f4e6aa)




<h2>2. Creating our own website</h2>

Default page is placed in /var/www/html/ location. You can place your static pages here, or use virtual host and place it other location.

(Virtual host is a method of hosting multiple domain names on the same server.)

Let’s create simple HTML page in /var/www/tutorial/ (it can be anything you want). Create index.html file in this location.

~cd /var/www

~sudo mkdir tutorial

~cd tutorial

~sudo "${EDITOR:-vi}" index.html



<h2>3. Setting up virtual host</h2>


To set up virtual host, we need to create file in /etc/nginx/sites-enabled/ directory.

For this, we will make our site available on 81 port, not the standard 80 port. You can change it if you would like to.

~cd /etc/nginx/sites-enabled

~sudo "${EDITOR:-vi}" tutorial => Save your configuration code here 


<h2>4. Activating virtual host and testing results</h2>

To make our site working, simply restart Nginx service.

~sudo service nginx restart

Let’s check if everything works as it should. Open our newly created site in web browser. Remember that we used :81 port.


  ![image](https://github.com/user-attachments/assets/e3fb6b41-c110-45e0-8ab4-ef7cafac6610)


We have just configured Nginx web server.




