# streamstation
dockerized streamingstation with telerix, icecast2 and liquidsoap

1. Download the Repository with git clone or as zip file
2. Change with your Terminal, Shell, PowerShell or CMD into the downloaded directory/repository
3. Execute command: "docker-compose up -d" 
4. When the docker services are established, open your browser and type: "localhost:9000" for Telerix and "localhost:8000" for Icecast
5. The login informations for Icecast: User: "admin" password: "set here your password"

If you wont to change your password for Icecast, please follow the instruction:
1. Open your Terminal, Shell, PowerShell or CMD and type command: "docker exec -it icecast /bin/bash"
2. Command: "su -"
3. Command: "vim /etc/icecast2/icecast.xml"
4. Command: ":37"
5. Command: "i"
6. go to password and change "set here your password" between the both tags < and > with the password you wont
7. do the same thing with all thre passwords you see in following rows
8. Command: Escape
9. Command: ":wq"
10. Command: "systemctl status icecast2" or if systemctl not booted "service icecast2 restart"
11. Clean your browser cache and reload the page, use now your new password
