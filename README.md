# linux-server-configuration
A project for Udacity's Full Stack Engineer Nanodegree

i. SSH to the server in the terminal: 54.245.167.183:2200

ii. URL to view the application in a web browser: http://ec2-54-245-167-183.us-west-2.compute.amazonaws.com/

iii. Changes made:
  - Implemented support for Item Catalog Application for PSQL, changes can be viewed at: https://github.com/Arjay123/fullstack-nanodegree-vm/tree/psql/vagrant/catalog
  
  - Edited Apache config file to use .WSGI file created to serve the application
  
  1. Set up UFW default rules:
      -sudo UFW default deny incoming
      -sudo UFW default allow outgoing
      
  2. Allow UFW Ports 80, 123, and 2200
      -sudo ufw allow 80
      -sudo ufw allow 123
      -sudo ufw allow 2200
      
  3. Edit sshd_config settings
      - set Port to 2200
      - set PermitRootLogin to no
      - set PasswordAuthentication to no
  
  4. Create new sudo user 'grader' and create ssh key on local machine
      - sudo adduser grader
      - sudo mkdir /Users/grader/.ssh
      - sudo nano /Users/grader/.ssh/authorized_keys <---- copy contents of local key into this file
      - sudo cp /etc/sudoers.d/90-cloud-init-users /etc/sudoers.d/grader
      - sudo nano /etc/sudoers.d/grader 
          .rename default user to 'grader'
  
  5. Update packages and set to auto-update
      - sudo apt-get update
      - sudo apt-get upgrade
      - sudo dpkg-reconfigure --priority=low unattended-upgrades
      
  6. Install apache and mod_wsgi
      - sudo apt-get install apache2 libapache2-mod-wsgi
      
  7. Create .wsgi file for project
      - sudo nano catalog.wsgi
  
  8. Edit default apache site to use .wsgi module to handle requests
      - sudo nano /etc/apache2/sites-enabled/000-default.conf
      - add line: WSGIScriptAlias / /var/www/html/catalog.wsgi
      
  
iv. A list of any third-party resources you made use of to complete this project.
  - Used Flask documentation: http://flask.pocoo.org/docs/0.12/deploying/mod_wsgi/
  - Used SQLAlchemy documentation: http://docs.sqlalchemy.org/en/latest/dialects/postgresql.html
  
