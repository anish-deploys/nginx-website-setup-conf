# Setting up virtual host for the website by Nginx 

<h1>What is Nginx?</h1>

Nginx (pronounced "engine-x") is an open-source web server software that is used to serve web content, handle reverse proxying, load balancing, and caching, among other things. It is highly scalable and efficient, designed to handle many simultaneous connections with minimal resource usage.

<h1>How Nginx Helps in Setting Up Virtual Hosts</h1>

<h4>Multiple Websites on One Server : </h4>

Virtual hosts allow you to host multiple websites on a single server, each with its own configuration. This is ideal for situations where you want to run several domains or subdomains on the same server.

<h4>Server Blocks for Each Website : </h4>

Nginx uses server blocks to define the settings for each website (virtual host). A server block specifies the domain name, document root, port, and other configurations for that particular site.

<h4>Domain-Based Virtual Hosting : </h4>

Nginx can serve different websites based on the domain name in the client request. This is the most common type of virtual hosting, called name-based virtual hosting.
For example, a single server could serve example1.com and example2.com with distinct content by configuring separate server blocks for each domain.

<h4>IP-Based or Port-Based Virtual Hosting :</h4>

You can also configure virtual hosts based on IP addresses or ports if you need different websites to respond on different IPs or ports.

# 1. Installing Nginx

    sudo apt update 

    sudo apt install nginx

Type "localhost" in your browser


  ![image](https://github.com/user-attachments/assets/271f46a5-92d3-4bd9-baaf-bd3692f4e6aa)




# 2. Creating our own website

Default page is placed in /var/www/html/ location. You can place your static pages here, or use virtual host and place it other location.

(Virtual host is a method of hosting multiple domain names on the same server.)

Let’s create simple HTML page in /var/www/tutorial/ (it can be anything you want). Create index.html file in this location.

    cd /var/www

    sudo mkdir tutorial

    cd tutorial

    sudo "${EDITOR:-vi}" index.html



# 3. Setting up virtual host


To set up virtual host, we need to create file in /etc/nginx/sites-enabled/ directory.

For this, we will make our site available on 81 port, not the standard 80 port. You can change it if you would like to.

    cd /etc/nginx/sites-enabled

    sudo "${EDITOR:-vi}" tutorial => Save your configuration code here 


# 4. Activating virtual host and testing results

To make our site working, simply restart Nginx service.

    sudo service nginx restart

Let’s check if everything works as it should. Open our newly created site in web browser. Remember that we used :81 port.


  ![image](https://github.com/user-attachments/assets/e3fb6b41-c110-45e0-8ab4-ef7cafac6610)


We have just configured Nginx web server.




