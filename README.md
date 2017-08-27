# linux-server-configuration
A project for Udacity's Full Stack Engineer Nanodegree

i. SSH to the server in the terminal: 54.245.167.183:2200

ii. URL to view the application in a web browser: http://ec2-54-245-167-183.us-west-2.compute.amazonaws.com/

iii. Changes made:
  - Implemented support for Item Catalog Application for PSQL, changes can be viewed at: https://github.com/Arjay123/fullstack-nanodegree-vm/tree/psql/vagrant/catalog
  
  - Edited Apache config file to use .WSGI file created to serve the application
  - Added server URL to list of authorized URLS in Google and Facebook Developer consoles for the Item Catalog application
  - Installed required python packages for application
  - Installed ubuntu packages: apache2, libapache2-mod-wsgi, postgresql
  - Edit UFW allowed ports: 2200, 80, 123
  
iv. A list of any third-party resources you made use of to complete this project.
  - Used Flask documentation: http://flask.pocoo.org/docs/0.12/deploying/mod_wsgi/
  - Used SQLAlchemy documentation: http://docs.sqlalchemy.org/en/latest/dialects/postgresql.html
  
