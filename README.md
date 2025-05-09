# BFTagCompose

This is a repository for the professional fire brigade day of the JF-Hechtsheim.

## Installation

Run the following commands in a Debian-like Linux distribution. Should also work on other distros with minor modifications. Only works on x86 archictectures.

```
sudo apt-get install docker-compose git
git clone https://github.com/Dakri7/BFTagCompose.git
cd BFTagCompose
sudo docker-compose up
```

## Configuration

The config file for the backend is in [backend/application.yml](backend/application.yml). Then run the following commands:
```
sudo docker-compose build
# I sometimes has problems without this
sudo docker-compose down
sudo docker-compose up
```

For the webserver the config file is in [web/environments.ts](web/environments.ts). Then run the same commands except for:
```
sudo docker-compose build --no-cache
# I sometimes has problems without this
sudo docker-compose down
sudo docker-compose up
```