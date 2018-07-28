Building a Mail Server
======================

This article was written and tested based off a server running Ubuntu 16.04 hosted by DigitalOcean. 

To get through this tutorial you will need:

* Ownership of a domain
* Access to the DNS records for that domain
* SSL/TLS setup on the domain
* If you wish to run the mail server off a subdomain, set up the subdomain before beginning

	Note: this is not the same as creating an online client for accessing emails. For example, I can have jonhutchens.com process incoming/outgoing mail while having a webmail client to access the emails available through mail.jonhutchens.com, but more on that later.

Let's get started!

Postfix
-------

The very first step is to create the mail server itself. We will do this using Postfix. First, make sure you are up to date with ``sudo apt update && sudo apt upgrade``. Now install postfix ``sudo apt install postfix``. Upon installing, postfix should prompt for several configuration settings to be initialized. If you do not see this prompt, postfix is likely already installed. In that case, ``sudo dpkg-reconfigure postfix`` should allow you to change the settings. Follow `this article <https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-postfix-on-ubuntu-16-04>`__ as a guide for what to put in these fields. Pay close attention to the "System mail name" and "Other destinations to accept mail for" fields.

The same article linked above has a good walkthrough for customizing the Maildir and email aliases. See steps 2-3 for how to do this (if you do setup the Maildir format, make sure you also follow step 5 to make sure the environment variables are properly set.

If you're using a firewall, make sure you allow postfix ``sudo ufw allow postfix``.

Step 6 and beyond (optional) describe setting up a specific email client that runs from the terminal. Follow those instructions if you are interested in doing that. 

Once finished, type ``mail`` to get into the mail client. Once inside you should see all emails in your inbox. While still inside here, you can type ``mail`` again to send an email. It will request a recipient address, Subject, and body (body is everything you type after hitting "Enter" on the Subject field - CTRL-D when you are done to send). 


