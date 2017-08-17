# factorioDocker

The simplest factorio docker image you can find. Run

    sudo docker run -p 34197:34197 --name factorio -it danielvestol/factorio:latest

To set a mod directory, do

    -v /srv/factorio/mods:/factorio/mods
    
To set a save directory

    -v /srv/factorio/saves:/factorio/saves


and it just works, connect with localhost or whatever fits you. Change first number to change the port it attaches to. To run a custom map:

download repository

edit dockerfile

uncomment COPY map.zip map.zip

comment out the line with RUN bin/x64/factorio --create saves/map.zip

place your map.zip in the same file as the dockerfile

build with > sudo docker build --force-rm -t danielvestol/factorio:latest --no-cache [Dockerfile directory]

#devs and other misc:

build with

    sudo docker build --force-rm -t danielvestol/factorio:latest factorioDocker

run with

    sudo docker run -p 34197:34197 --name factorio -it danielvestol/factorio:latest

to run unattended in the background, do

    sudo docker run -p 34197:34197 --name factorio -d danielvestol/factorio:latest
