# docker-nextcloud-mariadb-onlyoffice

Document Server and Nextcloud Docker installation
Document Server and Nextcloud Docker installation will install the preconfigured version of ONLYOFFICE Document Server connected to Nextcloud to your server running them in Docker containers.

Requirements
The latest version of Docker (can be downloaded here: https://docs.docker.com/engine/installation/)
Docker compose (can be downloaded here: https://docs.docker.com/compose/install/)
Installation
Get the latest version of this repository running the command:

'git clone --recursive https://github.com/sirvantis/docker-nextcloud-mariadb-onlyoffice'
cd docker-onlyoffice-nextcloud-mysql

Run Docker Compose:

docker-compose up -d
Please note: you might need to wait a couple of minutes when all the containers are up and running after the above command.

Now launch the browser and enter the webserver address. The Nextcloud wizard webpage will be opened. Enter all the necessary data to complete the wizard.

Once the setup wizard has completed, from your dashboard, go into Settings and look inside of your Apps section.

Inside of your Apps section, select the Integration menu on the left side. Find the OnlyOffice App, Download & Enable it.

Go to the project folder and run the set_configuration.sh script:

bash set_configuration.sh
Now you can enter Nextcloud and create a new document. It will be opened in ONLYOFFICE Document Server.
