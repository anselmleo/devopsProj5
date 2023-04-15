### DEMO

- Step 1: Launch two aws ubuntu instances for mysql server and mysql client
- Step 2: Update and Upgrade package repositories
- Step 3: Install mysql server on instance a
- Step 4: Install mysql client on instance b
- Step 5: On mysql server instance, locate the mysql configuration file and allow remote access

<img width="639" alt="Screen Shot 2023-04-15 at 3 14 13 PM" src="https://user-images.githubusercontent.com/30025376/232234194-41af4b42-306e-45d6-873c-862a2ad746d2.png">

- Step 6:  Confirm with netstat command (sudo netstat -tulnp | grep mysqld) that configuration works, and mysql listens on 0.0.0.0:3306

<img width="964" alt="Screen Shot 2023-04-15 at 3 37 27 PM" src="https://user-images.githubusercontent.com/30025376/232234257-663afabd-84f4-42ba-b667-11f0e4cb168d.png">

- Step 7: Open instance port 3306 by adding a security group

<img width="1091" alt="Screen Shot 2023-04-15 at 3 34 01 PM" src="https://user-images.githubusercontent.com/30025376/232234465-9af2d6dc-95ad-464a-b51b-8804663ee630.png">

- Step 8: Use nmap to confirm open ports nmap -Pn <public ip>
- Step 9: Create a remote user on mysql server
- Step 10: Flush privileges and grant privileges to new remote user.
- Step 11: Go back to client instance and initiate a remote connection (mysql -h hostip -u remoteuser -p) 
  
<img width="1440" alt="Screen Shot 2023-04-15 at 3 57 55 PM" src="https://user-images.githubusercontent.com/30025376/232234546-50870996-3dfc-4127-a89b-5c20dde02dc8.png">

🍻
