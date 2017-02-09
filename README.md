# plesk-autodiscover
AutoDiscover Addon for Plesk PANEL
Automatically Addon to Autoinstall Microsoft Outlook Clients without many work.

Solves PLESK SSL Certificate Error because of multiple Domain name with Dovecot, Courrier, Postfix

1. Preparation
   a) Install the Let's Encrypt Module
   b) Create a Default Server Domain with the Server's Hostname
   c) Create a Let's Encrypt Certificate
   d) Under Tools&Settings -> SSL & Certificates, select the certificate for the Default Hostname under Mail Server
   
2. Install


  a) Deploy package to /var/www/autodiscover
  b) Follow the Instructions at DomainPreset.INSTALL and NGINXPreset.INSTALL
  c) Reconfigure All HOSTS
  
     Run in shell:
     
     /usr/local/psa/admin/sbin/httpdmng --reconfigure-all
     
  d) All Hosts which should have AutoDiscover must have a Certificate (no need to enable it as default, Let's encrypt is ok)
  e) For default, the Server's Hostname which is in the certificate will be used for IMAP and SMTP.
     If you need per Host config, edit the config.php in the /var/www/autodiscover directory. You can enable additional Services like POP3
     

