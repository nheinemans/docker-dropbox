# docker-dropbox
# Purpose
Create a container running the Dropbox client.

# First start
First start the container with a console attached. The dropbox process will initialize the configuration and ask to be linked to an account.

	sudo docker run -h dropbox --name=dropbox -v /dropbox/config:/home/.dropbox -v /dropbox/files:/home/Dropbox -v /etc/localtime:/etc/localtime:ro nheinemans/dropbox

# Start the container
After the first start, the container can be stopped and started without a console.

    sudo docker stop dropbox
    sudo docker start dropbox

# dropbox.py command
In order to check the status of the dropbox sync, and make modifications (e.g. folder exclusions), I've include the dropbox.py command. It can be invoked with the following command:
    sudo docker exec -it dropbox dropbox.py

# Disclaimer
I'm in no way affiliated to Dropbox and cannot support its products. I just needed a working dropbox client on my docker based home-server.
