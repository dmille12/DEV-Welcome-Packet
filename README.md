# DEV-Welcome-Packet
DEV New Hires

NOTE: AN IT request must be submitted when the new hire is official to create four (4) linux VMs.

open a ticket with IT to get copies of the servercentral.com SSL certificate 

Determine which system will be the new hire’s mysql system—typically the “inventory system” is chosen. 
install mysql-server on it 
  apt-get mysql-server

Import the five (5) DB’s (the new hire will need to ask IT for backups of the current QA DB’s)
update the mysql config 
  /etc/mysql/mysql.conf.d/mysqld.conf 
set the bind-address to 
  0.0.0.0 
set sql_mode to: 
  NO_ZERO_IN_DATE
  ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER
  NO_ENGINE_SUBSTITUTION 

Restart mysql.

create a user and grant them access in mysql:
  CREATE USER ‘scnet’@’%’ IDENTIFIED BY ‘password’
  GRANT ALL PRIVILEGES ON * . * TO ‘scnet’@’%’
  FLUSH PRIVILEGES

Once complete, the new hire can start setting up the four (4) systems for development.
