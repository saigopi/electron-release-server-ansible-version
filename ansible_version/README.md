>A node web server which serves & manages releases of the your Electron App, and is fully compatible with Squirrel Auto-updater (which is built into Electron).

>Add the inventory file. 

>>Step1.
>cat /etc/ansible/inventory
>[local]
>192.168.0.YIP  ansible_user=root
#YIP - your server ip where you are going to install Electron.

>>Step2.
>And create data base. 
>follow this orginal version to create the database - and add only the host ip in the local.js file. you can change this the var file. 
>https://github.com/ArekSredzki/electron-release-server/blob/master/docs/database.md

>Or step2:  follow this - 
>Install postgresql ---- if you already install skip this steps. 
>create postgres user and password. and ---- if you already have one skip this steps.
>login to postqres as postgres user. and creat the following databse as same here. 


>CREATE ROLE electron_release_server_user ENCRYPTED PASSWORD '<PASSWORD>' LOGIN;

>CREATE DATABASE electron_release_server OWNER "electron_release_server_user";

>CREATE DATABASE electron_release_server_sessions OWNER "electron_release_server_user";

>once created install the electron release server. 

>RUN Ansible command
>>>#ansible-playbook -k maya_electron_playbook.yml -i inventory 


>>>>NOTE: IN PRODUCTION add local.js file in the gitignore file.