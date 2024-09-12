## Document Server and Nextcloud Docker installation
Tested on  Nextcloud Hub 8 (29.0.5), Onlyoffice Document Server 8.1.1.26, Mariadb 11.5.2
## Requirements

* The latest version of Docker (can be downloaded here: [https://docs.docker.com/engine/installation/](https://docs.docker.com/engine/installation/))
* Docker compose (can be downloaded here: [https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/))


## Installation

1. Get this repository running the command:

    ```
    git clone https://github.com/sirvantis/docker-nextcloud-mariadb-onlyoffice/
    ```

2. Run Docker Compose:

    **Please note**: the action must be performed with **root** rights.

    ```
    docker compose up -d
    ```

    **Please note**: you might need to wait a couple of minutes when all the containers are up and running after the above command.

3. Now launch the browser and enter the webserver address. The Nextcloud wizard webpage will be opened. Enter all the necessary data to complete the wizard.

4. Once the setup wizard has completed, from your dashboard, go into Settings and look inside of your Apps section.
Inside of your Apps section, select the Integration menu on the left side. Find the OnlyOffice App, Download & Enable it.

5. Go to the project folder and run this commands:

    **Please note**: the action must be performed with **root** rights.

    ```
    chmod +x set_configuration.sh
    bash set_configuration.sh
    ```
6. (Optional) You can check state of your ONLYOFFICE server by this command:
   ```
   docker exec -u www-data app-server php occ onlyoffice:documentserver --check
   ```
**Please note**: The default JWT (secret key) is enabled in ONLYOFFICE Document Server. It is recommended to specify your own secret key in the Nextcloud administrative configuration and [ONLYOFFICE Docs](https://helpcenter.onlyoffice.com/installation/docs-configure-jwt.aspx).

Now you can enter Nextcloud and create a new document. It will be opened in ONLYOFFICE Document Server. 
