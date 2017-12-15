# csc400
Refer to the wiki tab for more information on the project.

Each of the programs are ran in /etc/crontab where they are scheduled to run at a certain time of the day.


client.py is on the client side and is used to communicate with the server that has server.py running and download the database of hostile IPs.

server.py uses sockets and allows network programming. This transfers the SQLite db, "ip.db" to as many clients as it wants.

update_fw.py is on the client side and updates the client's firewall with new, unique IPs from the server.

update_db.py is on the server side and updates the database with new, unique IPs.

get_ips.sh is a shellscript on the server that reads through the firewall logs and takes the source IPs and places them into a text file: hostile_ips.txt

hostile_ips.txt is the output of the program get_ips.sh which are then placed in the database: ip.db.

crontab_server is the crontab on the server that schedules the programs to run at a certain time. 
crontab_client is the crontab on the client that schedules the programs to run at a certain time

